---
title: "&lt;deque&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 482d7c92-54c7-493b-99e6-2a73617481a5
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 18fafc735fe05dbba24058394bbcd7fefd45cffd
ms.lasthandoff: 02/24/2017

---
# <a name="ltdequegt-operators"></a>&lt;deque&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체와 같지 않은지 테스트합니다.  
  
```
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `deque` 형식의 개체입니다.  
  
 `right`  
 `deque` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 deque 개체가 같지 않으면 **true**이고, deque 개체가 같으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 deque 개체는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// deque_op_ne.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c2.push_back( 2 );  
  
   if ( c1 != c2 )  
      cout << "The deques are not equal." << endl;  
   else  
      cout << "The deques are equal." << endl;  
}  
\* Output:   
The deques are not equal.  
*\  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 작은지 테스트합니다.  
  
```
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `deque` 형식의 개체입니다.  
  
 `right`  
 `deque` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 deque가 연산자 우변의 deque보다 작으며 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 작음 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// deque_op_lt.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 < c2 )  
      cout << "Deque c1 is less than deque c2." << endl;  
   else  
      cout << "Deque c1 is not less than deque c2." << endl;  
}  
\* Output:   
Deque c1 is less than deque c2.  
*\   
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 작거나 같은지 테스트합니다.  
  
```
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `deque` 형식의 개체입니다.  
  
 `right`  
 `deque` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 deque가 연산자 우변의 deque보다 작거나 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 작거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// deque_op_le.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 <= c2 )  
      cout << "Deque c1 is less than or equal to deque c2." << endl;  
   else  
      cout << "Deque c1 is greater than deque c2." << endl;  
}  
\* Output:   
Deque c1 is less than or equal to deque c2.  
*\  
  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체와 같은지 테스트합니다.  
  
```
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `deque` 형식의 개체입니다.  
  
 `right`  
 `deque` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 deque가 연산자 우변의 deque와 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 deque는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// deque_op_eq.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c2.push_back( 1 );  
  
   if ( c1 == c2 )  
      cout << "The deques are equal." << endl;  
   else  
      cout << "The deques are not equal." << endl;  
  
   c1.push_back( 1 );  
   if ( c1 == c2 )  
      cout << "The deques are equal." << endl;  
   else  
      cout << "The deques are not equal." << endl;  
}  
\* Output:   
The deques are equal.  
The deques are not equal.  
*\  
  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 큰지 테스트합니다.  
  
```
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `deque` 형식의 개체입니다.  
  
 `right`  
 `deque` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 deque가 연산자 우변의 deque보다 크면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 큼 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// deque_op_gt.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 > c2 )  
      cout << "Deque c1 is greater than deque c2." << endl;  
   else  
      cout << "Deque c1 is not greater than deque c2." << endl;  
}  
\* Output:   
Deque c1 is greater than deque c2.  
*\  
  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 크거나 같은지 테스트합니다.  
  
```
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `deque` 형식의 개체입니다.  
  
 `right`  
 `deque` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 deque가 연산자 우변의 deque보다 크거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 크거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// deque_op_ge.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2;  
  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 >= c2 )  
      cout << "Deque c1 is greater than or equal to deque c2." << endl;  
   else  
      cout << "Deque c1 is less than deque c2." << endl;  
}  
\* Output:   
Deque c1 is greater than or equal to deque c2.  
*\  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<deque>](../standard-library/deque.md)




