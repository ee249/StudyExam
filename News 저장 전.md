```java
package my.spring.springnews;
import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.servlet.ModelAndView;

import dao.NewsDAO;
import vo.NewsVO;
@Controller
public class NewsController {
	@Autowired
	NewsDAO dao;
	
	@RequestMapping("/newsmain")
	public String form() {
		return "News";
	}
	
	@RequestMapping(value = "/news", method = RequestMethod.GET)
	public ModelAndView proc(String newsid, String action, String writer, String type, String cc) {
		ModelAndView mav = new ModelAndView();
		List<NewsVO> list = null;
		NewsVO vo1 = null;
		int gab = 0;
		if(newsid != null)
			gab = Integer.parseInt(newsid);
		
		if(action==null) {
			if(newsid==null) {
				list = dao.listAll();
				for (NewsVO vo : list) {
					System.out.println(vo.getTitle());
				}
				mav.addObject("list", list);
			}
		}
		else if(action.equals("read")) {
			if (gab == 0) {
				mav.addObject("msg", newsid + "가 id인 글이 없어요");
			} else {
				vo1 = dao.listOne(gab);
				list = dao.listAll();
				mav.addObject("vo1", vo1);
				mav.addObject("list", list);
			}	
		}
		else if(action.equals("delete")) {
				dao.delete(gab); 
				vo1 = dao.listOne(gab);
				list = dao.listAll();
				mav.addObject("list", list);
				mav.addObject("vo1", vo1);
		}
		else if(action.equals("search")) {
			if(cc!=null) {
			list=dao.search(cc, type);
			mav.addObject("list", list);
			System.out.println(list);
			}
		}
		else if(action.equals("listwriter")) {
			list=dao.listWriter(writer);
			mav.addObject("list", list);
			System.out.println(list);
		}
		mav.setViewName("News");
		return mav;
	}
	
	
	
	@RequestMapping(value = "/news", method = RequestMethod.POST) 
	public ModelAndView proc1(String writer, String title, String content, String action, String newsid) {
		ModelAndView mav = new ModelAndView();
		NewsDAO dao = new NewsDAO(); 
		NewsVO vo = new NewsVO();
		List<NewsVO> list = null;
		 if(action.equals("insert")) {
			  vo.setWriter(writer); 
			  vo.setTitle(title); 
			  vo.setContent(content);
			  boolean result = dao.insert(vo); 

			  if(result) {
				  mav.addObject("msg",writer+"님의 글이 성공적으로 입력되었어요!!..");
				  list = dao.listAll();
				  mav.addObject("list", list);
			  } else { 
				  mav.addObject("msg", writer+"님의 글이 입력에 실패했어요!!");
			 }	  
		  }
		  
		  else{
				vo.setId(Integer.parseInt(newsid));
				vo.setWriter(writer);
				vo.setTitle(title);
				vo.setContent(content);
				boolean result = dao.update(vo);
				if (result) {			
					mav.addObject("msg", writer + "님의 글이 성공적으로 수정되었습니다.");			
				} else {
					mav.addObject("msg", writer + "님의 글이 수정되지 않았습니다.");
				}
				mav.addObject("list", dao.listAll());
			}
		mav.setViewName("News");
		return mav;
	}
	 
}

```

