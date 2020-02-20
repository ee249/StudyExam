#### 게시판 만들기(select 부분)

※ Hashmap 이용(News 게시판)

- Mapper

```xml
</select>
<select id="searchNews" parameterType="java.util.HashMap"resultType="vo.NewsVO">
select id, writer, title, content, to_char(writedate,'yyyy"년"mm"월"dd"일"') writedate, cnt from News where ${type} like '%'||#{window}||'%'
</select>
```

\- <select> 안에 있는 id는 select를 대표하는 명입니다. 이 아이디로 인해서 DAO에 있는 session.selectList 부분에 statement 부분으로 들어간다.

\- HashMap 타입으로 입력받기 때문에 parameterType을 "java.util.HashMap"로 설정하고 결과는 NewVO 리턴되기 때문에 resultType은 "vo.NewsVO"로 한다.

\- type 은 query문을 입력 받는 것이라 선택받는 select option tag에서 설정된 정보를 입력 받는 것이기 때문에 ${type} 이렇게 써야 한다.

\- window는 query문을 직접 입력 받는 것이기 때문에 #{window} 이렇게 작성해야 한다.

- DAO

```java
  public List<NewsVO> search(String window, String type){
		List<NewsVO> list = new ArrayList<>();
		Map<String,String> map= new HashMap<String,String>();
		map.put("window", window); // key, value
		map.put("type", type); // key, value
		String statement = "resource.NewsMapper.searchNews"; // 여기
		list=session.selectList(statement, map);
		return list;
	  }
```

\- List<NewsVO> list = new ArrayList<>(); List가 ArrayList의 부모임으로 List로 해도 ArrayList 타입의 변수를 list로 생성할 수 있다.

\- Map<String, String> map = new HashMap<String, String>(); Map이 HashMap의 부모임으로 Map르로 해도 HashMap 타입의 변수를 map으로 생성할 수 있다.

\- map.put("window", window); map.put("type", type);  

- Controller 부분

```java
else if(action.equals("search")) {
			if(window!=null) {
			list=dao.search(window, type);
			mav.addObject("list", list);
			}
		}
```

이 과정이 지나면 view로 넘어가서 출력이 된다.