---
title: "back_insert_iterator 클래스 | Microsoft Docs"
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
  - "iterator/std::back_insert_iterator"
  - "std::back_insert_iterator"
  - "back_insert_iterator"
  - "std.back_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_insert_iterator 클래스"
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# back_insert_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

출력 반복기의 요구 사항을 충족하는 반복기 어댑터에 대해 설명합니다. 반복기 어댑터는 요소를 덮어쓰는 것이 아니라, 시퀀스 끝 부분에 요소를 삽입하므로 C++ 시퀀스 컨테이너의 반복기가 제공한 덮어쓰기 의미 체계와 다른 의미 체계를 제공합니다. `back_insert_iterator` 클래스는 컨테이너 형식에 대해 템플릿화됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Container`  
 `back_insert_iterator`가 뒤에 요소를 삽입할 컨테이너의 형식입니다.  
  
## <a name="remarks"></a>설명  
 컨테이너는 가능할 경우 시퀀스 끝에 분할된 시간으로 요소를 삽입하는 후면 삽입 시퀀스에 대한 요구 사항을 충족해야 합니다. 정의한 STL 시퀀스 컨테이너는 [deque 클래스](../standard-library/deque-class.md), [list 클래스](../standard-library/list-class.md) 및 [vector 클래스](../standard-library/vector-class.md) 는 필요한 제공 `push_back` 멤버 함수를 이러한 요구 사항을 충족 합니다. 이러한 세 컨테이너와 문자열은 각각 `back_insert_iterator`와 함께 사용하도록 조정할 수 있습니다. `back_insert_iterator`는 항상 컨테이너를 사용하여 초기화해야 합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator__back_insert_iterator)|컨테이너의 마지막 요소 다음에 요소를 삽입하는 `back_insert_iterator`를 만듭니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[container_type](#back_insert_iterator__container_type)|`back_insert_iterator`에 대한 컨테이너를 제공하는 형식입니다.|  
|[참조](#back_insert_iterator__reference)|`back_insert_iterator`에 대한 참조를 제공하는 형식입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 *](#back_insert_iterator__operator_star)|출력 반복기 식을 구현 하는 데 사용 된 역참조 연산자 * `i` = `x` 후면 삽입을 위해.|  
|[operator + +](#back_insert_iterator__operator_add_add)|값을 저장할 다음 위치에 `back_insert_iterator`를 증가시킵니다.|  
|[연산자 =](#back_insert_iterator__operator_eq)|출력 반복기 식을 구현 하는 데 사용 되는 할당 연산자 * `i` = `x` 후면 삽입을 위해.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \< 반복기>  
  
 **네임스페이스:** std  
  
##  <a name="a-namebackinsertiteratorbackinsertiteratora-backinsertiteratorbackinsertiterator"></a><a name="back_insert_iterator__back_insert_iterator"></a>  back_insert_iterator:: back_insert_iterator  
 컨테이너의 마지막 요소 다음에 요소를 삽입하는 `back_insert_iterator`를 만듭니다.  
  
```  
 
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Cont`  
 컨테이너는는 `back_insert_iterator` 에 요소를 삽입 하는 것입니다.  
  
### <a name="return-value"></a>반환 값  
 A `back_insert_iterator` 컨테이너에서 매개 변수입니다.  
  
### <a name="example"></a>예제  
  
```  
// back_insert_iterator_back_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The initial vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   // Insertions with member function  
   back_inserter ( vec ) = 40;  
   back_inserter ( vec ) = 50;  
  
   // Alternatively, insertions can be done with template function  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 600;  
   backiter++;  
 *backiter = 700;  
  
   cout << "After the insertions, the vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The initial vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).  
```  
  
##  <a name="a-namebackinsertiteratorcontainertypea-backinsertiteratorcontainertype"></a><a name="back_insert_iterator__container_type"></a>  back_insert_iterator:: container_type  
 `back_insert_iterator`에 대한 컨테이너를 제공하는 형식입니다.  
  
```  
 
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 템플릿 매개 변수는 동의어 **컨테이너**합니다.  
  
### <a name="example"></a>예제  
  
```  
// back_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The original vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::container_type vec1 = vec;  
   back_inserter ( vec1 ) = 40;  
  
   cout << "After the insertion, the vector is: ( ";  
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector vec is: ( 1 2 3 ).  
After the insertion, the vector is: ( 1 2 3 40 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatorstara-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_star"></a>  back_insert_iterator:: operator *  
 출력 반복기 식을 구현 하는 데 사용 된 역참조 연산자 \* *i* = *x*합니다.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>반환 값  
 컨테이너 뒤에 있는 삽입 된 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 출력 반복기 식을 구현 하는 데 **\*Iter** = **값**합니다. 경우 **Iter** 는 시퀀스의 요소를 다음 주소를 지정 하는 반복기는 **\*Iter** = **값** 값으로 해당 요소를 대체 하 고 시퀀스에 있는 요소의 총 수를 변경 되지 않습니다.  
  
### <a name="example"></a>예제  
  
```  
// back_insert_iterator_back_insert.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatoraddadda-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_add_add"></a>  back_insert_iterator:: operator + +  
 값을 저장할 다음 위치에 `back_insert_iterator`를 증가시킵니다.  
  
```  
back_insert_iterator<Container>& operator++();

back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>반환 값  
 A `back_insert_iterator` 값 수 저장한 다음 위치를 주소 지정 합니다.  
  
### <a name="remarks"></a>설명  
 Preincrementation와 postincrementation 연산자는 동일한 결과 반환합니다.  
  
### <a name="example"></a>예제  
  
```  
// back_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 3 ; ++i )    
   {  
      vec.push_back ( 10 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 30;  
   backiter++;      // Increment to the next element  
 *backiter = 40;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 10 20 ).  
After the insertions, the vector vec becomes: ( 10 20 30 40 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatoreqa-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_eq"></a>  back_insert_iterator:: operator =  
 추가 또는 컨테이너의 백 엔드에 값을 푸시합니다.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);

    back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
 ` val`  
 컨테이너에 삽입할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 삽입 된 컨테이너 뒤에 있는 마지막 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 연산자 평가 `Container.push_back( val)`,  
  
 그런 다음 반환 `*this`합니다. 두 번째 멤버 연산자 평가  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 그런 다음 반환 `*this`합니다.  
  
### <a name="example"></a>예제  
  
```  
// back_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="a-namebackinsertiteratorreferencea-backinsertiteratorreference"></a><a name="back_insert_iterator__reference"></a>  back_insert_iterator:: reference  
 `back_insert_iterator`에 대한 참조를 제공하는 형식입니다.  
  
```  
 
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>설명  
 연관된 컨테이너에서 제어 되는 시퀀스의 요소에 대 한 참조를 설명 하는 형식입니다.  
  
### <a name="example"></a>예제  
  
```  
// back_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::reference   
        RefLast = *(vec.end ( ) - 1 );  
   cout << "The last element in the vector vec is: "   
        << RefLast << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
The last element in the vector vec is: 3.  
```  
  
## <a name="see-also"></a>참고 항목  
 [\< 반복기>](../standard-library/iterator.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

