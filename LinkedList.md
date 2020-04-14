##  LinkedList

: LinkedList에서 가장 중요한 것이 바로 노드의 구현입니다. 

1. 노드는 실제로 데이터가 저장되는 그릇과 같은 것이기 떄문에 가장 먼저 해야한다.
2. 자바는 객체지향  언어이기 때문에 노드는 객체로 만들기 좋습니다.
3. 노드 객체는 리스트의 내부 부품이기 때문에 외부에는 노출되지 않는 것이 좋습니다.(private 지정)
4. 사용자는 이 객체에 대해서 알 필요가 없고 단지 값을 넣고 빼는 것으로 충분합니다.



#### 내용

-  head는 첫번째 노드를 지정하는 참조값입니다. tail은 마지막 노드를 지정합니다. size는 노드의 크기를 의미합니다.
- 객체 Node는 내부적으로 data와 next 변수를 가지고 있습니다. data는 노드의 값이고, next는 다음 노드를 참조값입니다.

```java
public class LinkedList{
	// 첫번째 노드를 가리키는 필드
    private Node head; // Node 객체를 가지고 있다.
    private Node tail;
    private int size = 0;
    private class Node{
        // 데이터가 저장될 필드
        private object data;
        // 다음 노드를 가리키는 필드
        private Node next;
        public Node(Object input){ // 생성자 함수
            this.data = input;
            this.next = null;
        }
        // 노드의 내용을 쉽게 출력해서 확인해볼 수 있는 기능
        public String toString(){
            return String.valueOf()
        }     
    } 
}
```

