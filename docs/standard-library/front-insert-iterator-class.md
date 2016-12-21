---
title: "front_insert_iterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::front_insert_iterator"
  - "std::front_insert_iterator"
  - "std.front_insert_iterator"
  - "front_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_insert_iterator 클래스"
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# front_insert_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

출력 반복기의 요구 사항을 충족하는 반복기 어댑터에 대해 설명합니다. 요소를 덮어쓰는 것이 아니라, 시퀀스 앞 부분에 요소를 삽입하므로 C++ 시퀀스 컨테이너의 반복기가 제공한 덮어쓰기 의미 체계와 다른 의미 체계를 제공합니다. `front_insert_iterator` 클래스는 컨테이너 형식에 대해 템플릿화됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Container`  
 `front_insert_iterator`가 앞에 요소를 삽입할 컨테이너의 형식입니다.  
  
## <a name="remarks"></a>설명  
 컨테이너는 가능할 경우 시퀀스 처음에 분할된 시간으로 요소를 삽입하는 전면 삽입 시퀀스에 대한 요구 사항을 충족해야 합니다. 정의한 표준 템플릿 라이브러리 시퀀스 컨테이너는 [deque 클래스](../standard-library/deque-class.md) 및 [list 클래스](../standard-library/list-class.md) 는 필요한 제공 `push_front` 멤버 함수를 이러한 요구 사항을 충족 합니다. 이와 반대로에서 정의한 시퀀스 컨테이너는 [vector 클래스](../standard-library/vector-class.md) 이러한 요구 사항을 충족 하지 않으며 함께 사용 하도록 조정할 수 없습니다 `front_insert_iterator`s. `front_insert_iterator`는 항상 컨테이너를 사용하여 초기화해야 합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|지정된 컨테이너 개체 앞에 요소를 삽입할 수 있는 반복기를 만듭니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|전면 삽입 대상인 컨테이너를 나타내는 형식입니다.|  
|[참조](#front_insert_iterator__reference)|연관 컨테이너에서 제어하는 시퀀스의 요소에 대한 참조를 제공하는 형식입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 *](#front_insert_iterator__operator_star)|출력 반복기 식을 구현 하는 데 사용 된 역참조 연산자 * `i` = `x` 전면 삽입을 위해.|  
|[operator + +](#front_insert_iterator__operator_add_add)|값을 저장할 다음 위치에 `front_insert_iterator`를 증가시킵니다.|  
|[연산자 =](#front_insert_iterator__operator_eq)|출력 반복기 식을 구현 하는 데 사용 되는 할당 연산자 * `i` = `x` 전면 삽입을 위해.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \< 반복기>  
  
 **네임스페이스:** std  
  
##  <a name="a-namefrontinsertiteratorcontainertypea-frontinsertiteratorcontainertype"></a><a name="front_insert_iterator__container_type"></a>  front_insert_iterator:: container_type  
 전면 삽입 대상인 컨테이너를 나타내는 형식입니다.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **컨테이너**합니다.  
  
### <a name="example"></a>예제  
  
```  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorfrontinsertiteratora-frontinsertiteratorfrontinsertiterator"></a><a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator:: front_insert_iterator  
 지정된 컨테이너 개체 앞에 요소를 삽입할 수 있는 반복기를 만듭니다.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Cont`  
 컨테이너 개체에는 `front_insert_iterator` 요소를 삽입 하는 것입니다.  
  
### <a name="return-value"></a>반환 값  
 A `front_insert_iterator` 매개 변수 컨테이너 개체에 대 한 합니다.  
  
### <a name="example"></a>예제  
  
```  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatorstara-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_star"></a>  front_insert_iterator:: operator *  
 해결할 수 있는 요소를 반환 하는 삽입 반복기를 역참조 합니다.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>반환 값  
 멤버 함수 주소를 지정 하는 요소의 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 출력 반복기 식을 구현 하는 데 **\*Iter** = **값**합니다. 경우 **Iter** 는 시퀀스의 요소를 다음 주소를 지정 하는 반복기는 **\*Iter** = **값** 값으로 해당 요소를 대체 하 고 시퀀스에 있는 요소의 총 수를 변경 되지 않습니다.  
  
### <a name="example"></a>예제  
  
```  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoraddadda-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator:: operator + +  
 값을 저장할 다음 위치에 `back_insert_iterator`를 증가시킵니다.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>반환 값  
 A `front_insert_iterator` 값 수 저장한 다음 위치를 주소 지정 합니다.  
  
### <a name="remarks"></a>설명  
 Preincrementation와 postincrementation 연산자는 동일한 결과 반환합니다.  
  
### <a name="example"></a>예제  
  
```  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoreqa-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator:: operator =  
 (푸시)를 추가 합니다. 컨테이너의 맨 앞에는 값입니다.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
 ` val`  
 컨테이너에 할당할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 컨테이너의 맨 앞에 삽입 된 마지막 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 연산자 평가 `container.push_front( val)`, 그런 다음 반환 `*this`합니다.  
  
 두 번째 멤버 연산자 평가  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 그런 다음 반환 `*this`합니다.  
  
### <a name="example"></a>예제  
  
```  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorreferencea-frontinsertiteratorreference"></a><a name="front_insert_iterator__reference"></a>  front_insert_iterator:: reference  
 연관 컨테이너에서 제어하는 시퀀스의 요소에 대한 참조를 제공하는 형식입니다.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>예제  
  
```  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>참고 항목  
 [\< 반복기>](../standard-library/iterator.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

