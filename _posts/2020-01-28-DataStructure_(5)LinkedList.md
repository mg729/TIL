---
title: "Data Structure - (5) 연결리스트"
categories:
  - Data Structure
tags:
  - Data Structure
link: https://mg729.github.io//data%20structure/2020/01/14/DataStructure_(5)_LinkedList/
---
##  Linked List (단순연결리스트의 구조)  
 ![sindly_linked_list](/images/Singly-linked-list.png)  
 *[singly linked list](https://en.wikipedia.org/wiki/Linked_list)* 

> **동적으로 크기가 변할 수 있고 삭제나 삽입 시에 데이터를 이동할 필요가 없는 구조**  
<ul>
<li>배열의 단점을 해결하는 자료구조</li>
<ul>  
<li>배열은 연결된 저장공간으로 미리 크기가<u>고정</u>된 데이터 구조</li>  
<li>이에 반해서 Linked List 는 미리 크기를 고정하지 않고 필요할때마다 <u>동적으로</u> 추가,삭제가 가능한 데이터구조</li> 
</ul> 
</ul>

<ul>
 <li> <b>노드(node)</b> : 데이터 저장단위 (데이터, 포인터로 구성) </li>
 <li> <b>포인터(pointer)</b> : 노드 안에서 노드의 다음 데이터에 대한 연결 정보(주소값)를 가지고 있는 공간 </li>
</ul>

<ul>
<li>Linked List 의 마지막 노드의 포인터는 <b>nullptr</b>로 설정</li>  
<ul><li>더이상 연결된 노드가 없다는 것을 의미</li></ul>
</ul>  

##  Linked List 의 장단점
1. 장점  
   * 미리 데이터 공간을 할당하지 않아도 됨  
2. 단점  
   * 저장 효율이 높지 않음 (데이터 뿐만아니라 연결을 위한 포인터 주소공간도 필요하므로)  
   * 연결정보를 찾는 시간이 필요하므로 접근 속도가 느림  
   * 중단 데이터 삭제시, 앞뒤 데이터의 연결을 재구성해야함  

# C++ Code
* [Linked List C++ code](https://www.codesdope.com/blog/article/c-linked-lists-in-c-singly-linked-list/)  
* *Below C++ code is for __Singly Linked List__*
> [Node 구현 & Linked List class 구현](#Node&LinkedList)   
> [Linked List 에 데이터 추가하기](#Add_data)  
> [Linked List 데이터 출력하기](#Print_data)  
> [Node 와 Node를 연결하기](#Node_concatenate)  
> [Linked List 데이터 사이에 데이터 추가하기](#Insert_data)  
> [데이터 삭제하기](#Delete_data)  
> [데이터 검색하기](#Search_data)  


## Node&LinkedList클래스
<details>
	<summary>Show C++ code</summary>
		<p>
		
			1. Struct를 이용하여 Node만들기  

			```c++  
			#incldue <iostream>
			using namespace std;

			struct node
			{
				int data;
				node *next;
			}
			\```  
			
			2. Class를 이용하여 linked_list 만들기  
			* singly linked list에서 first node는 반드시 알고 있어야합니다.      
				* first node를 통해서 전체 list에 접근하므로    
				* first node를 **head**라고 함  

			```c++  
			#include <iostream>
			using namespace std;

			struct node
			{
				int data;
				node *next;
			}; //expected ';' after struct definition 

			class LinkedList
			{
				private:
					node *head, *tail;
				public:
					LinkedList()
					{
						head = nullptr;
						tail = nullptr;
					}
			}; //expected ';' after class definition 

			int main()
			{
				LinkedList l;
				return 0;
			}
			\```  
			
			* expected **';'** after struct definition     
			* expected **';'** after class definition  
			* class LinkedList **()**  : () is unqualified  
			* `node* head, tail;` : tail은 node*가 아니라 node타입으로 선언됨  
				* node * head, tail; (x)
				* node *head, *tail; (o)
		</p>	
</details>
