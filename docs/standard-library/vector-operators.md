---
title: "&lt;vector&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 14308c0789851af423fd687f88acfe9177d89aff
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  operator!=  
 연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.  
  
```  
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **vector** 형식의 개체입니다.  
  
 `right`  
 **vector** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 벡터가 같지 않으면 **true**이고 벡터가 같으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 벡터는 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_ne.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
     v2.push_back( 2 );  
  
   if ( v1 != v2 )  
      cout << "Vectors not equal." << endl;  
   else  
      cout << "Vectors equal." << endl;  
}  
```  
  
```Output  
Vectors not equal.  
```  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작은지 테스트합니다.  
  
```  
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **vector** 형식의 개체입니다.  
  
 `right`  
 **vector** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 벡터가 연산자 우변의 벡터보다 작으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_lt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 < v2 )  
      cout << "Vector v1 is less than vector v2." << endl;  
   else  
      cout << "Vector v1 is not less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than vector v2.  
```  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작거나 같은지 테스트합니다.  
  
```  
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **vector** 형식의 개체입니다.  
  
 `right`  
 **vector** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 벡터가 연산자 우변의 벡터보다 작거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_le.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 <= v2 )  
      cout << "Vector v1 is less than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than or equal to vector v2.  
```  
  
##  <a name="operator_eq_eq"></a>  operator==  
 연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.  
  
```  
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **vector** 형식의 개체입니다.  
  
 `right`  
 **vector** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 벡터가 연산자 우변의 벡터와 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 벡터는 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v2.push_back( 1 );  
  
   if ( v1 == v2 )  
      cout << "Vectors equal." << endl;  
   else  
      cout << "Vectors not equal." << endl;  
}  
```  
  
```Output  
Vectors equal.  
```  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 연산자의 좌변에 있는 개체가 우변에 있는 개체보다 큰지 테스트합니다.  
  
```  
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **vector** 형식의 개체입니다.  
  
 `right`  
 **vector** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 벡터가 연산자 우변의 벡터보다 크면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_gt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
   v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 > v2 )  
      cout << "Vector v1 is greater than vector v2." << endl;  
   else  
      cout << "Vector v1 is not greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than vector v2.  
```  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 연산자의 좌변에 있는 개체가 우변에 있는 개체보다 크거나 같은지 테스트합니다.  
  
```  
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 **vector** 형식의 개체입니다.  
  
 `right`  
 **vector** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 벡터가 벡터 우변의 벡터보다 크거나 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_ge.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
     v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 >= v2 )  
      cout << "Vector v1 is greater than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than or equal to vector v2.  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<vector>](../standard-library/vector.md)


