---
title: "reverse_iterator 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reverse_iterator
- std::reverse_iterator
- std.reverse_iterator
- xutility/std::reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- reverse_iterator class
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: ff83cfe68b15e1e94328e96dcd6f33f266bf531a
ms.lasthandoff: 02/24/2017

---
# <a name="reverseiterator-class"></a>reverse_iterator 클래스
템플릿 클래스는 임의 액세스, 양방향 반복기 또는 역방향으로만 동작하는 역방향 반복기 개체에 대해 설명하는 반복기 어댑터입니다. 범위를 뒤로 이동할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### <a name="parameters"></a>매개 변수  
 RandomIterator  
 반복기를 조정하여 역방향으로 작동할 수 있는 형식입니다.  
  
## <a name="remarks"></a>설명  
 기존 C++ 표준 라이브러리에는 `reverse_iterator` 및 `const_reverse_iterator` 형식이 정의되어 있으며 역방향 반복기를 반환하는 구성원 함수 `rbegin` 및 `rend`가 있습니다. 이러한 반복기는 덮어쓰기 의미 체계가 있습니다. `reverse_iterator` 어댑터는 이 기능을 제안 삽입 의미 체계로 보완하며 스트림과 함께 사용할 수 있습니다.  
  
 양방향 반복기가 필요한 `reverse_iterator`는 `operator+=`, `operator+`, `operator-=`, `operator-`, `operator[]` 멤버 함수 전부를 호출하지 않아야 합니다. 이러한 멤버 함수는 임의 액세스 반복기에서만 사용해야 합니다.  
  
 반복기의 범위가 [ ` first`,  last)일 경우 왼쪽 대괄호는 \_ *First*에서 포함함을 나타내고, 오른쪽의 괄호는 \_ *Left*까지의 요소를 포함함을 나타내지만, \_ *Left*자체는 제외합니다. 동일한 요소가 역방향 시퀀스 [ **rev** â€“ ` first`, **rev** â€“ \_ *Left*)에 포함된 경우 \_ *Left*가 시퀀스에서 끝 요소 하나 다음에 있으면 역방향 시퀀스의 첫 번째 요소 **rev** â€“ \_ *First*는 \*(\_ *Left* â€“ 1 )을 가리킵니다. 모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.  
  
 &\*( **reverse_iterator** ( *i* ) ) == &\*( *i* â€“ 1 ).  
  
 실제로, 역방향 시퀀스에서 reverse_iterator는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의(오른쪽으로) 요소를 참조함을 의미합니다. 따라서 반복기가 시퀀스(2, 4, 6, 8)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스(8, 6, 4, 2)에서 요소 4를 주소 지정합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[reverse_iterator](#reverse_iterator__reverse_iterator)|기본 반복기에서 기본 `reverse_iterator` 또는 `reverse_iterator`를 생성합니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[difference_type](#reverse_iterator__difference_type)|동일한 컨테이너 안에서 요소를 참조하는 두 `reverse_iterator` 사이의 차이를 제공하는 형식입니다.|  
|[iterator_type](#reverse_iterator__iterator_type)|`reverse_iterator`의 기본 반복기를 제공하는 형식입니다.|  
|[pointer](#reverse_iterator__pointer)|`reverse_iterator`로 주소를 지정하는 요소에 포인터를 제공하는 형식입니다.|  
|[reference](#reverse_iterator__reference)|`reverse_iterator`로 주소를 지정하는 요소에 참조를 제공하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[base](#reverse_iterator__base)|`reverse_iterator`에서 기본 반복기를 복구합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator_star](#reverse_iterator__operator_star)|`reverse_iterator`가 주소 지정하는 요소를 반환합니다.|  
|[operator+](#reverse_iterator__operator_add)|반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `reverse_iterator`를 반환합니다.|  
|[operator++](#reverse_iterator__operator_add_add)|`reverse_iterator`를 다음 요소로 증가시킵니다.|  
|[operator+=](#reverse_iterator__operator_add_eq)|`reverse_iterator`에서 지정된 오프셋을 추가합니다.|  
|[operator-](#reverse_iterator__operator-)|`reverse_iterator`에서 오프셋을 차감하고 오프셋 위치에서 요소를 주소 지정하는 `reverse_iterator`를 반환합니다.|  
|[operator--](#reverse_iterator__operator--)|`reverse_iterator`를 이전 요소로 감소시킵니다.|  
|[operator-=](#reverse_iterator__operator-_eq)|`reverse_iterator`에서 지정된 오프셋을 차감합니다.|  
|[operator->](#reverse_iterator__operator-_gt_)|`reverse_iterator`가 주소 지정하는 요소로 포인터를 반환합니다.|  
|[operator&#91;&#93;](#reverse_iterator__operator_at)|`reverse_iterator`에서 주소 지정하는 요소의 요소 오프셋으로 지정된 위치 수만큼 참조를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<iterator>  
  
 **네임스페이스:** std  
  
##  <a name="a-namereverseiteratorbasea--reverseiteratorbase"></a><a name="reverse_iterator__base"></a>  reverse_iterator::base  
 `reverse_iterator`에서 기본 반복기를 복구합니다.  
  
```   
RandomIterator base() const;
```  
  
### <a name="return-value"></a>반환 값  
 `reverse_iterator`의 기본이 되는 반복기입니다.  
  
### <a name="remarks"></a>설명  
 모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.  
  
 &\*( `reverse_iterator` ( *i* ) ) == &\*( *i* â€“ 1 ).  
  
 실제로, 역방향 시퀀스에서 `reverse_iterator`는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의(오른쪽으로) 요소를 참조함을 의미합니다. 따라서 반복기가 시퀀스(2, 4, 6, 8)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스(8, 6, 4, 2)에서 요소 4를 주소 지정합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_base.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos, bpos;  
   pos = find ( vec.begin ( ), vec.end ( ), 6 );  
   cout << "The iterator pos points to: " << *pos << "." << endl;  
  
   typedef reverse_iterator<vector<int>::iterator>::iterator_type it_vec_int_type;  
  
   reverse_iterator<it_vec_int_type> rpos ( pos );  
   cout << "The reverse_iterator rpos points to: " << *rpos   
        << "." << endl;  
  
   bpos = rpos.base ( );  
   cout << "The iterator underlying rpos is bpos & it points to: "   
        << *bpos << "." << endl;  
}  
```  
  
##  <a name="a-namereverseiteratordifferencetypea--reverseiteratordifferencetype"></a><a name="reverse_iterator__difference_type"></a>  reverse_iterator::difference_type  
 동일한 컨테이너 안에서 요소를 참조하는 두 `reverse_iterator` 사이의 차이를 제공하는 형식입니다.  
  
```   
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type; 
```  
  
### <a name="remarks"></a>설명  
 `reverse_iterator` 차이 형식은 반복기 차이 형식과 같습니다.  
  
 형식은 반복기 특성 형식 이름 `iterator_traits`\< **RandomIterator**> **::pointer**와 동일한 의미입니다.  
  
### <a name="example"></a>예제  
  `difference_type`을 선언하고 사용하는 방법의 예제는 [reverse_iterator::operator&#91;&#93;](#reverse_iterator__operator_at)를 참조하세요.  
  
##  <a name="a-namereverseiteratoriteratortypea--reverseiteratoriteratortype"></a><a name="reverse_iterator__iterator_type"></a>  reverse_iterator::iterator_type  
 `reverse_iterator`의 기본 반복기를 제공하는 형식입니다.  
  
```  
typedef RandomIterator iterator_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Iterator`의 동의어입니다.  
  
### <a name="example"></a>예제  
  `iterator_type`을 선언하고 사용하는 방법의 예제는 [reverse_iterator::base](#reverse_iterator__base)를 참조하세요.  
  
##  <a name="a-namereverseiteratoroperatorstara--reverseiteratoroperator"></a><a name="reverse_iterator__operator_star"></a>  reverse_iterator::operator*  
 reverse_iterator가 주소를 지정하는 요소를 반환합니다.  
  
```   
reference operator*() const;
```  
  
### <a name="return-value"></a>반환 값  
 reverse_iterator에 의해 주소가 지정되는 요소값입니다.  
  
### <a name="remarks"></a>설명  
 연산자는 \*( **current** â€“ 1)을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_ref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos, bpos;  
   pos = find ( vec.begin ( ), vec.end ( ), 6 );  
  
   // Declare a difference type for a parameter  
   // declare a reference return type  
   reverse_iterator<vector<int>::iterator>::reference refpos = *pos;  
   cout << "The iterator pos points to: " << refpos << "." << endl;  
}  
```  
  
##  <a name="a-namereverseiteratoroperatoradda--reverseiteratoroperator"></a><a name="reverse_iterator__operator_add"></a>  reverse_iterator::operator+  
 반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `reverse_iterator`를 반환합니다.  
  
```  
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `Off`  
 역방향 반복기에 추가할 오프셋입니다.  
  
### <a name="return-value"></a>반환 값  
 오프셋 요소의 주소를 지정하는 `reverse_iterator`입니다.  
  
### <a name="remarks"></a>설명  
 이 구성원 함수는 `reverse_iterator`가 임의 액세스 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_add.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   vector <int>::reverse_iterator rVPOS2 =rVPOS1 + 2; // offset added  
   cout << "After the +2 offset, the iterator rVPOS2 points\n"  
        << " to the 3rd element in the reversed sequence: "  
        << *rVPOS2 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 10.  
After the +2 offset, the iterator rVPOS2 points  
 to the 3rd element in the reversed sequence: 6.  
```  
  
##  <a name="a-namereverseiteratoroperatoraddadda--reverseiteratoroperator"></a><a name="reverse_iterator__operator_add_add"></a>  reverse_iterator::operator++  
 reverse_iterator를 이전 요소로 증가시킵니다.  
  
```  
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 연산자는 사전 증가된 `reverse_iterator`를 반환하고, 두 번째(사후 증가) 연산자는 증가된 `reverse_iterator`의 복사본을 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 구성원 함수는 `reverse_iterator`가 양방향 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i - 1 );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the last element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1++;  // postincrement, preincrement: ++rVPSO1  
  
   cout << "After incrementing, the iterator rVPOS1 points\n"  
        << " to the second element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 3 5 7 9 ).  
The vector vec reversed is: ( 9 7 5 3 1 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 9.  
After incrementing, the iterator rVPOS1 points  
 to the second element in the reversed sequence: 7.  
```  
  
##  <a name="a-namereverseiteratoroperatoraddeqa--reverseiteratoroperator"></a><a name="reverse_iterator__operator_add_eq"></a>  reverse_iterator::operator+=  
 reverse_iterator에서 지정된 오프셋을 추가합니다.  
  
```  
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```  
  
### <a name="parameters"></a>매개 변수  
 `Off`  
 반복기를 증가시킬 오프셋입니다.  
  
### <a name="return-value"></a>반환 값  
 `reverse_iterator`에서 주소를 지정한 요소에 대한 참조입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_addoff.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )   
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the last element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1+=2;   // addition of an offset  
   cout << "After the +2 offset, the iterator rVPOS1 now points\n"  
        << " to the third element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 10.  
After the +2 offset, the iterator rVPOS1 now points  
 to the third element in the reversed sequence: 6.  
```  
  
##  <a name="a-namereverseiteratoroperator-a--reverseiteratoroperator-"></a><a name="reverse_iterator__operator-"></a>  reverse_iterator::operator-  
 `reverse_iterator`에서 오프셋을 차감하고 오프셋 위치에서 요소를 주소 지정하는 `reverse_iterator`를 반환합니다.  
  
```  
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `Off`  
 reverse_iterator에서 뺄 오프셋입니다.  
  
### <a name="return-value"></a>반환 값  
 오프셋 요소의 주소를 지정하는 `reverse_iterator`입니다.  
  
### <a name="remarks"></a>설명  
 이 구성원 함수는 `reverse_iterator`가 임의 액세스 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_sub.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 3 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   vector <int>::reverse_iterator rVPOS2 =rVPOS1 - 2; // offset subtracted  
   cout << "After the -2 offset, the iterator rVPOS2 points\n"  
        << " to the 2nd element from the last in the reversed sequence: "  
        << *rVPOS2 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 3 6 9 12 15 ).  
The vector vec reversed is: ( 15 12 9 6 3 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 3.  
After the -2 offset, the iterator rVPOS2 points  
 to the 2nd element from the last in the reversed sequence: 9.  
```  
  
##  <a name="a-namereverseiteratoroperator--a--reverseiteratoroperator--"></a><a name="reverse_iterator__operator--"></a>  reverse_iterator::operator--  
 reverse_iterator를 이전 요소로 감소시킵니다.  
  
```  
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 연산자는 사전 감소된 `reverse_iterator`를 반환하고, 두 번째(사후 감소) 연산자는 감소된 `reverse_iterator`의 복사본을 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 구성원 함수는 `reverse_iterator`가 양방향 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_decr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i - 1 );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
   rVPOS1--;  // postdecrement, predecrement: --rVPSO1  
  
   cout << "After the decrement, the iterator rVPOS1 points\n"  
        << " to the next-to-last element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 3 5 7 9 ).  
The vector vec reversed is: ( 9 7 5 3 1 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 1.  
After the decrement, the iterator rVPOS1 points  
 to the next-to-last element in the reversed sequence: 3.  
```  
  
##  <a name="a-namereverseiteratoroperator-eqa--reverseiteratoroperator-"></a><a name="reverse_iterator__operator-_eq"></a>  reverse_iterator::operator-=  
 `reverse_iterator`에서 지정된 오프셋을 차감합니다.  
  
```  
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```  
  
### <a name="parameters"></a>매개 변수  
 `Off`  
 `reverse_iterator`에서 뺄 오프셋입니다.  
  
### <a name="remarks"></a>설명  
 이 구성원 함수는 `reverse_iterator`가 임의 액세스 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.  
  
 연산자가 **current** + _ *Off*를 평가합니다. 그런 다음 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_op_suboff.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 3 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1-=2;      // Subtraction of an offset  
   cout << "After the -2 offset, the iterator rVPOS1 now points\n"  
        << " to the 2nd element from the last in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 3 6 9 12 15 ).  
The vector vec reversed is: ( 15 12 9 6 3 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 3.  
After the -2 offset, the iterator rVPOS1 now points  
 to the 2nd element from the last in the reversed sequence: 9.  
```  
  
##  <a name="a-namereverseiteratoroperator-gta--reverseiteratoroperator-gt"></a><a name="reverse_iterator__operator-_gt_"></a>  reverse_iterator::operator-&gt;  
 `reverse_iterator`가 주소 지정하는 요소로 포인터를 반환합니다.  
  
```   
pointer operator->() const;
```  
  
### <a name="return-value"></a>반환 값  
 `reverse_iterator`에서 주소를 지정한 요소에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는 **&\*\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_ptrto.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef vector<pair<int,int> > pVector;  
   pVector vec;  
   vec.push_back(pVector::value_type(1,2));  
   vec.push_back(pVector::value_type(3,4));  
   vec.push_back(pVector::value_type(5,6));  
  
   pVector::iterator pvIter;  
   cout << "The vector vec of integer pairs is:\n( ";  
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)  
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";  
   cout << ")" << endl << endl;  
  
   pVector::reverse_iterator rpvIter;  
   cout << "The vector vec reversed is:\n( ";  
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++ )  
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";  
   cout << ")" << endl << endl;  
  
   pVector::iterator pos = vec.begin ( );  
   pos++;  
   cout << "The iterator pos points to:\n( " << pos -> first << ", "   
   << pos -> second << " )" << endl << endl;  
  
   pVector::reverse_iterator rpos (pos);   
  
   // Use operator -> with return type: why type int and not int*  
   int fint = rpos -> first;  
   int sint = rpos -> second;  
  
   cout << "The reverse_iterator rpos points to:\n( " << fint << ", "   
   << sint << " )" << endl;  
}  
```  
  
```Output  
The vector vec of integer pairs is:  
( ( 1, 2) ( 3, 4) ( 5, 6) )  
  
The vector vec reversed is:  
( ( 5, 6) ( 3, 4) ( 1, 2) )  
  
The iterator pos points to:  
( 3, 4 )  
  
The reverse_iterator rpos points to:  
( 1, 2 )  
```  
  
##  <a name="a-namereverseiteratoroperatorata--reverseiteratoroperator"></a><a name="reverse_iterator__operator_at"></a>  reverse_iterator::operator[]  
 `reverse_iterator`에서 주소 지정하는 요소의 요소 오프셋으로 지정된 위치 수만큼 참조를 반환합니다.  
  
```   
reference operator[](difference_type Off) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `Off`  
 `reverse_iterator` 주소의 오프셋입니다.  
  
### <a name="return-value"></a>반환 값  
 요소 오프셋에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는 **\***( **\*this** + `Off`)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_ret_ref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos;  
   pos = find ( vec.begin ( ), vec.end ( ), 8 );  
   reverse_iterator<vector<int>::iterator> rpos ( pos );  
  
   // Declare a difference type for a parameter  
   reverse_iterator<vector<int>::iterator>::difference_type diff = 2;  
  
   cout << "The iterator pos points to: " << *pos << "." << endl;  
   cout << "The iterator rpos points to: " << *rpos << "." << endl;  
  
   // Declare a reference return type & use operator[]  
   reverse_iterator<vector<int>::iterator>::reference refrpos = rpos [diff];  
   cout << "The iterator rpos now points to: " << refrpos << "." << endl;     
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator pos points to: 8.  
The iterator rpos points to: 6.  
The iterator rpos now points to: 2.  
```  
  
##  <a name="a-namereverseiteratorpointera--reverseiteratorpointer"></a><a name="reverse_iterator__pointer"></a>  reverse_iterator::pointer  
 `reverse_iterator`로 주소를 지정하는 요소에 포인터를 제공하는 형식입니다.  
  
```  
typedef typename iterator_traits<RandomIterator>::pointer pointer;  
```  
  
### <a name="remarks"></a>설명  
 형식은 반복기 특성 형식 이름 `iterator_traits`\< *RandomIterator*> **::pointer**와 동일한 의미입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_pointer.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef vector<pair<int,int> > pVector;  
   pVector vec;  
   vec.push_back( pVector::value_type( 1,2 ) );  
   vec.push_back( pVector::value_type( 3,4 ) );  
   vec.push_back( pVector::value_type( 5,6 ) );  
  
   pVector::iterator pvIter;  
   cout << "The vector vec of integer pairs is:\n" << "( ";  
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)  
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";  
   cout << ")" << endl;  
  
   pVector::reverse_iterator rpvIter;  
   cout << "\nThe vector vec reversed is:\n" << "( ";  
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++)  
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";  
   cout << ")" << endl;  
  
   pVector::iterator pos = vec.begin ( );  
   pos++;  
   cout << "\nThe iterator pos points to:\n"  
        << "( " << pos -> first << ", "  
        << pos -> second << " )" << endl;  
  
   pVector::reverse_iterator rpos (pos);  
   cout << "\nThe iterator rpos points to:\n"  
        << "( " << rpos -> first << ", "  
        << rpos -> second << " )" << endl;  
}  
```  
  
```Output  
The vector vec of integer pairs is:  
( ( 1, 2) ( 3, 4) ( 5, 6) )  
  
The vector vec reversed is:  
( ( 5, 6) ( 3, 4) ( 1, 2) )  
  
The iterator pos points to:  
( 3, 4 )  
  
The iterator rpos points to:  
( 1, 2 )  
```  
  
##  <a name="a-namereverseiteratorreferencea--reverseiteratorreference"></a><a name="reverse_iterator__reference"></a>  reverse_iterator::reference  
 reverse_iterator로 주소를 지정하는 요소에 참조를 제공하는 형식입니다.  
  
```  
typedef typename iterator_traits<RandomIterator>::reference reference;  
```  
  
### <a name="remarks"></a>설명  
 형식은 반복기 특성 형식 이름 `iterator_traits`\< *RandomIterator*> **::reference**와 동일한 의미입니다.  
  
### <a name="example"></a>예제  
  **reference**를 선언하고 사용하는 방법의 예제는 [reverse_iterator::operator&#91;&#93;](#reverse_iterator__operator_at) 또는 [reverse_iterator::operator*](#reverse_iterator__operator_star)를 참조하세요.  
  
##  <a name="a-namereverseiteratorreverseiteratora--reverseiteratorreverseiterator"></a><a name="reverse_iterator__reverse_iterator"></a>  reverse_iterator::reverse_iterator  
 기본 반복기에서 기본 `reverse_iterator` 또는 `reverse_iterator`를 생성합니다.  
  
```   
reverse_iterator();  
explicit reverse_iterator(RandomIterator right);

template <class Type>  
reverse_iterator(const reverse_iterator<Type>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 `reverse_iterator`로 조정할 반복기입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 반복기를 조정하는 기본 `reverse_iterator` 또는 `reverse_iterator`입니다.  
  
### <a name="remarks"></a>설명  
 모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.  
  
 &\*( `reverse_iterator` ( *i* ) ) == &\*( *i* â€“ 1 ).  
  
 실제로, 역방향 시퀀스에서 reverse_iterator는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의(오른쪽으로) 요소를 참조함을 의미합니다. 따라서 반복기가 시퀀스(2, 4, 6, 8)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스(8, 6, 4, 2)에서 요소 4를 주소 지정합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// reverse_iterator_reverse_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos;  
   pos = find ( vec.begin ( ), vec.end ( ), 4 );  
   cout << "The iterator pos = " << *pos << "." << endl;  
  
   vector <int>::reverse_iterator rpos ( pos );  
   cout << "The reverse_iterator rpos = " << *rpos   
        << "." << endl;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)


