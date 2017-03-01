---
title: "&lt;set&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4256ebc-c449-4688-95db-fced42d20d4d
caps.latest.revision: 8
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8a527297ac01359a19f4d5951bb25fcff2dceb5d
ms.lasthandoff: 02/24/2017

---
# <a name="ltsetgt-operators"></a>&lt;set&gt; 연산자
||||  
|-|-|-|  
|[operator!= (set)](#operator_neq)|[operator&gt; (set)](#operator_gt_)|[operator&gt;= (set)](#operator_gt__eq)|  
|[operator&lt; (set)](#operator_lt_)|[operator&lt;= (set)](#operator_lt__eq)|[operator== (set)](#operator_eq_eq)|  
|[operator!= (multiset)](#operator_neq_multiset)|[operator&gt; (multiset)](#operator_gt_multiset)|[operator&gt;= (multiset)](#operator_gt__eq_multiset)|  
|[operator&lt; (multiset)](#operator_lt_multiset)|[operator&lt;= (multiset)](#operator_lt__eq_multiset)|[operator== (multiset)](#operator_eq_eq_multiset)|  
  
##  <a name="a-nameoperatorneqa--operator-set"></a><a name="operator_neq"></a>  operator!= (set)  
 연산자의 좌변에 있는 set 개체가 우변에 있는 set 개체와 같지 않은지 테스트합니다.  
  
```
bool operator!=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **set** 형식의 개체입니다.  
  
 `right`  
 **set** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 집합이 같으면 **true**이고 집합이 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 set 개체 간의 비교는 해당 요소 간의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 집합은 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// set_op_ne.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 != s2 )  
      cout << "The sets s1 and s2 are not equal." << endl;  
   else  
      cout << "The sets s1 and s2 are equal." << endl;  
  
   if ( s1 != s3 )  
      cout << "The sets s1 and s3 are not equal." << endl;  
   else  
      cout << "The sets s1 and s3 are equal." << endl;  
}  
\* Output:   
The sets s1 and s2 are not equal.  
The sets s1 and s3 are equal.  
*\  
```  
  
##  <a name="a-nameoperatorlta--operatorlt-set"></a><a name="operator_lt_"></a>  operator&lt; (set)  
 연산자의 좌변에 set 개체가 우변에 있는 set 개체보다 작은지 테스트합니다.  
  
```
bool operator<(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **set** 형식의 개체입니다.  
  
 `right`  
 **set** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 set가 연산자 우변의 set보다 엄격하게 작으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 set 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 작음 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// set_op_lt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 < s2 )  
      cout << "The set s1 is less than the set s2." << endl;  
   else  
      cout << "The set s1 is not less than the set s2." << endl;  
  
   if ( s1 < s3 )  
      cout << "The set s1 is less than the set s3." << endl;  
   else  
      cout << "The set s1 is not less than the set s3." << endl;  
}  
\* Output:   
The set s1 is less than the set s2.  
The set s1 is not less than the set s3.  
*\  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt-set"></a><a name="operator_lt__eq"></a>  operator&lt;= (set)  
 연산자의 좌변에 있는 set 개체가 우변에 있는 set 개체보다 작거나 같은지 테스트합니다.  
  
```
bool operator!<=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **set** 형식의 개체입니다.  
  
 `right`  
 **set** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 set가 연산자 우변의 set보다 작거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 set 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 작거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// set_op_le.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 <= s2 )  
      cout << "Set s1 is less than or equal to the set s2." << endl;  
   else  
      cout << "The set s1 is greater than the set s2." << endl;  
  
   if ( s1 <= s3 )  
      cout << "Set s1 is less than or equal to the set s3." << endl;  
   else  
      cout << "The set s1 is greater than the set s3." << endl;  
  
   if ( s1 <= s4 )  
      cout << "Set s1 is less than or equal to the set s4." << endl;  
   else  
      cout << "The set s1 is greater than the set s4." << endl;  
}  
\* Output:   
Set s1 is less than or equal to the set s2.  
The set s1 is greater than the set s3.  
Set s1 is less than or equal to the set s4.  
*\  
```  
  
##  <a name="a-nameoperatoreqeqa--operator-set"></a><a name="operator_eq_eq"></a>  operator== (set)  
 연산자의 좌변에 있는 set 개체가 우변에 있는 set 개체와 같은지 테스트합니다.  
  
```
bool operator!==(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **set** 형식의 개체입니다.  
  
 `right`  
 **set** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 set가 연산자 우변의 set와 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 set 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 집합은 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// set_op_eq.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The sets s1 and s2 are equal." << endl;  
   else  
      cout << "The sets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The sets s1 and s3 are equal." << endl;  
   else  
      cout << "The sets s1 and s3 are not equal." << endl;  
}  
\* Output:   
The sets s1 and s2 are not equal.  
The sets s1 and s3 are equal.  
*\  
```  
  
##  <a name="a-nameoperatorgta--operatorgt-set"></a><a name="operator_gt_"></a>  operator&gt; (set)  
 연산자의 좌변에 있는 set 개체가 우변에 있는 set 개체보다 큰지 테스트합니다.  
  
```
bool operator>(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **set** 형식의 개체입니다.  
  
 `right`  
 **set** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 set가 연산자 우변의 set보다 크면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 set 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 큼 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// set_op_gt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 > s2 )  
      cout << "The set s1 is greater than the set s2." << endl;  
   else  
      cout << "The set s1 is not greater than the set s2." << endl;  
  
   if ( s1 > s3 )  
      cout << "The set s1 is greater than the set s3." << endl;  
   else  
      cout << "The set s1 is not greater than the set s3." << endl;  
}  
\* Output:   
The set s1 is not greater than the set s2.  
The set s1 is greater than the set s3.  
*\  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt-set"></a><a name="operator_gt__eq"></a>  operator&gt;= (set)  
 연산자의 좌변에 있는 set 개체가 우변에 있는 set 개체보다 크거나 같은지 테스트합니다.  
  
```
bool operator!>=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **set** 형식의 개체입니다.  
  
 `right`  
 **set** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 set가 연산자 우변의 set보다 크거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 set 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 크거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// set_op_ge.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 >= s2 )  
      cout << "Set s1 is greater than or equal to set s2." << endl;  
   else  
      cout << "The set s1 is less than the set s2." << endl;  
  
   if ( s1 >= s3 )  
      cout << "Set s1 is greater than or equal to set s3." << endl;  
   else  
      cout << "The set s1 is less than the set s3." << endl;  
  
   if ( s1 >= s4 )  
      cout << "Set s1 is greater than or equal to set s4." << endl;  
   else  
      cout << "The set s1 is less than the set s4." << endl;  
}  
\* Output:   
The set s1 is less than the set s2.  
Set s1 is greater than or equal to set s3.  
Set s1 is greater than or equal to set s4.  
*\  
```  
  
##  <a name="a-nameoperatorneqmultiseta--operator-multiset"></a><a name="operator_neq_multiset"></a>  operator!= (multiset)  
 연산자의 좌변에 있는 multiset 개체가 우변에 있는 multiset 개체와 같지 않은지 테스트합니다.  
  
```
bool operator!=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `multiset` 형식의 개체입니다.  
  
 `right`  
 `multiset` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 multiset가 같으면 **true**이고 multiset가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 multiset 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 set 또는 multiset는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// multiset_op_ne.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 != s2 )  
      cout << "The multisets s1 and s2 are not equal." << endl;  
   else  
      cout << "The multisets s1 and s2 are equal." << endl;  
  
   if ( s1 != s3 )  
      cout << "The multisets s1 and s3 are not equal." << endl;  
   else  
      cout << "The multisets s1 and s3 are equal." << endl;  
}  
\* Output:   
The multisets s1 and s2 are not equal.  
The multisets s1 and s3 are equal.  
*\  
```  
  
##  <a name="a-nameoperatorltmultiseta--operatorlt-multiset"></a><a name="operator_lt_multiset"></a>  operator&lt; (multiset)  
 연산자의 좌변에 있는 multiset 개체가 우변에 있는 multiset 개체보다 작은지 테스트합니다.  
  
```
bool operator<(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `multiset` 형식의 개체입니다.  
  
 `right`  
 `multiset` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 multiset가 연산자 우변의 multiset보다 엄격하게 작으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 multiset 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 작음 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// multiset_op_lt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 < s2 )  
      cout << "The multiset s1 is less than "  
           << "the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is not less than "  
           << "the multiset s2." << endl;  
  
   if ( s1 < s3 )  
      cout << "The multiset s1 is less than "  
           << "the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is not less than "  
           << "the multiset s3." << endl;  
}  
\* Output:   
The multiset s1 is less than the multiset s2.  
The multiset s1 is not less than the multiset s3.  
*\  
```  
  
##  <a name="a-nameoperatorlteqmultiseta--operatorlt-multiset"></a><a name="operator_lt__eq_multiset"></a>  operator&lt;= (multiset)  
 연산자의 좌변에 있는 multiset 개체가 우변에 있는 multiset 개체보다 작거나 같은지 테스트합니다.  
  
```
bool operator!<=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `multiset` 형식의 개체입니다.  
  
 `right`  
 `multiset` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 multiset가 연산자 우변의 multiset보다 작거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 multiset 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 작거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// multiset_op_le.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 <= s2 )  
      cout << "The multiset s1 is less than "  
           << "or equal to the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is greater than "  
           << "the multiset s2." << endl;  
  
   if ( s1 <= s3 )  
      cout << "The multiset s1 is less than "  
           << "or equal to the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is greater than "  
           << "the multiset s3." << endl;  
  
   if ( s1 <= s4 )  
      cout << "The multiset s1 is less than "  
           << "or equal to the multiset s4." << endl;  
   else  
      cout << "The multiset s1 is greater than "  
           << "the multiset s4." << endl;  
}  
\* Output:   
The multiset s1 is less than or equal to the multiset s2.  
The multiset s1 is greater than the multiset s3.  
The multiset s1 is less than or equal to the multiset s4.  
*\  
```  
  
##  <a name="a-nameoperatoreqeqmultiseta--operator-multiset"></a><a name="operator_eq_eq_multiset"></a>  operator== (multiset)  
 연산자의 좌변에 있는 multiset 개체가 우변에 있는 multiset 개체와 같은지 테스트합니다.  
  
```
bool operator!==(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `multiset` 형식의 개체입니다.  
  
 `right`  
 `multiset` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 multiset가 연산자 우변의 multiset와 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 multiset 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 set 또는 multiset는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// multiset_op_eq.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The multisets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The multisets s1 and s3 are equal." << endl;  
   else  
      cout << "The multisets s1 and s3 are not equal." << endl;  
}  
\* Output:   
The multisets s1 and s2 are not equal.  
The multisets s1 and s3 are equal.  
*\  
```  
  
##  <a name="a-nameoperatorgtmultiseta--operatorgt-multiset"></a><a name="operator_gt_multiset"></a>  operator&gt; (multiset)  
 연산자의 좌변에 있는 multiset 개체가 우변에 있는 multiset 개체보다 큰지 테스트합니다.  
  
```
bool operator>(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `multiset` 형식의 개체입니다.  
  
 `right`  
 `multiset` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 multiset가 연산자 우변의 multiset보다 크면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 multiset 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 큼 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// multiset_op_gt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 > s2 )  
      cout << "The multiset s1 is greater than "  
           << "the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is not greater "  
           << "than the multiset s2." << endl;  
  
   if ( s1 > s3 )  
      cout << "The multiset s1 is greater than "  
           << "the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is not greater than "  
           << "the multiset s3." << endl;  
}  
\* Output:   
The multiset s1 is not greater than the multiset s2.  
The multiset s1 is greater than the multiset s3.  
*\  
```  
  
##  <a name="a-nameoperatorgteqmultiseta--operatorgt-multiset"></a><a name="operator_gt__eq_multiset"></a>  operator&gt;= (multiset)  
 연산자의 좌변에 있는 multiset 개체가 우변에 있는 multiset 개체보다 크거나 같은지 테스트합니다.  
  
```
bool operator!>=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `multiset` 형식의 개체입니다.  
  
 `right`  
 `multiset` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 multiset가 연산자 우변의 multiset보다 크거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 multiset 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 크거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// multiset_op_ge.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 >= s2 )  
      cout << "The multiset s1 is greater than "  
           << "or equal to the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is less than "  
           << "the multiset s2." << endl;  
  
   if ( s1 >= s3 )  
      cout << "The multiset s1 is greater than "  
           << "or equal to the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is less than "  
           << "the multiset s3." << endl;  
  
   if ( s1 >= s4 )  
      cout << "The multiset s1 is greater than "  
           << "or equal to the multiset s4." << endl;  
   else  
      cout << "The multiset s1 is less than "  
           << "the multiset s4." << endl;  
}  
\* Output:   
The multiset s1 is less than the multiset s2.  
The multiset s1 is greater than or equal to the multiset s3.  
The multiset s1 is greater than or equal to the multiset s4.  
*\  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<set>](../standard-library/set.md)




