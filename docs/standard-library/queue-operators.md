---
title: "&lt;queue&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c435b48-175c-45b0-88eb-24561044019c
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3160c7fb3965bc05ceace5722a9c502e60f89442
ms.lasthandoff: 02/24/2017

---
# <a name="ltqueuegt-operators"></a>&lt;queue&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체와 같지 않은지 테스트합니다.  
  
```  
bool operator!=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 **queue** 형식의 개체입니다.  
  
 ` right`  
 **queue** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 queue가 같으면 **true**이고 queue가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 queue 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 큐는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// queue_op_ne.cpp  
// compile with: /EHsc  
#include <queue>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queues with list base containers  
   queue <int, list<int> > q1, q2, q3;  
  
   // The following line would have caused an error because vector   
   // does not support pop_front( ) and so cannot be adapted  
   // by queue as a base container  
   // queue <int, vector<int> > q1, q2, q3;  
  
   q1.push( 1 );  
   q2.push( 1 );  
   q2.push( 2 );  
   q3.push( 1 );  
  
   if ( q1 != q2 )  
      cout << "The queues q1 and q2 are not equal." << endl;  
   else  
      cout << "The queues q1 and q2 are equal." << endl;  
  
   if ( q1 != q3 )  
      cout << "The queues q1 and q3 are not equal." << endl;  
   else  
      cout << "The queues q1 and q3 are equal." << endl;  
}  
```  
  
```Output  
The queues q1 and q2 are not equal.  
The queues q1 and q3 are equal.  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 작은지 테스트합니다.  
  
```  
bool operator<(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 **queue** 형식의 개체입니다.  
  
 ` right`  
 **queue** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 queue가 연산자 우변의 queue보다 작으며 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 queue 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 queue 개체 간의 보다 작음 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// queue_op_lt.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2, q3;  
  
   q1.push( 1 );  
   q1.push( 2 );  
   q2.push( 5 );  
   q2.push( 10 );  
   q3.push( 1 );  
   q3.push( 2 );  
  
   if ( q1 < q2 )  
      cout << "The queue q1 is less than the queue q2." << endl;  
   else  
      cout << "The queue q1 is not less than the queue q2." << endl;  
  
   if ( q1 < q3 )  
      cout << "The queue q1 is less than the queue q3." << endl;  
   else  
      cout << "The queue q1 is not less than the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is less than the queue q2.  
The queue q1 is not less than the queue q3.  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 작거나 같은지 테스트합니다.  
  
```  
bool operator<=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 **queue** 형식의 개체입니다.  
  
 ` right`  
 **queue** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 queue가 연산자 우변의 queue보다 엄격하게 작으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 queue 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 queue 개체 간의 작거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// queue_op_le.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2, q3;  
  
   q1.push( 5 );  
   q1.push( 10 );  
   q2.push( 1 );  
   q2.push( 2 );  
   q3.push( 5 );  
   q3.push( 10 );  
  
   if ( q1 <= q2 )  
      cout << "The queue q1 is less than or equal to "  
           << "the queue q2." << endl;  
   else  
      cout << "The queue q1 is greater than "  
           << "the queue q2." << endl;  
  
   if ( q1 <= q3 )  
      cout << "The queue q1 is less than or equal to "  
           << "the queue q3." << endl;  
   else  
      cout << "The queue q1 is greater than "  
           << "the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is greater than the queue q2.  
The queue q1 is less than or equal to the queue q3.  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 연산자의 좌변에 있는 queue 개체가 우변에 있는 queue 개체와 같은지 테스트합니다.  
  
```  
bool operator==(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 **queue** 형식의 개체입니다.  
  
 ` right`  
 **queue** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 queue가 같으면 **true**이고 queue가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 queue 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 큐는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// queue_op_eq.cpp  
// compile with: /EHsc  
#include <queue>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queues with list base containers  
   queue <int, list<int> > q1, q2, q3;  
  
   // The following line would have caused an error because vector   
   // does not support pop_front( ) and so cannot be adapted  
   // by queue as a base container  
   // queue <int, vector<int> > q1, q2, q3;  
  
   q1.push( 1 );  
   q2.push( 2 );  
   q3.push( 1 );  
  
   if ( q1 != q2 )  
      cout << "The queues q1 and q2 are not equal." << endl;  
   else  
      cout << "The queues q1 and q2 are equal." << endl;  
  
   if ( q1 != q3 )  
      cout << "The queues q1 and q3 are not equal." << endl;  
   else  
      cout << "The queues q1 and q3 are equal." << endl;  
}  
```  
  
```Output  
The queues q1 and q2 are not equal.  
The queues q1 and q3 are equal.  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 큰지 테스트합니다.  
  
```  
bool operator>(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 **queue** 형식의 개체입니다.  
  
 ` right`  
 **queue** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 queue가 연산자 우변의 queue보다 엄격하게 작으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 queue 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 queue 개체 간의 보다 큼 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// queue_op_gt.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2, q3;  
  
   q1.push( 1 );  
   q1.push( 2 );  
   q1.push( 3 );  
   q2.push( 5 );  
   q2.push( 10 );  
   q3.push( 1 );  
   q3.push( 2 );  
  
   if ( q1 > q2 )  
      cout << "The queue q1 is greater than "  
           << "the queue q2." << endl;  
   else  
      cout << "The queue q1 is not greater than "  
           << "the queue q2." << endl;  
  
   if ( q1> q3 )  
      cout << "The queue q1 is greater than "  
           << "the queue q3." << endl;  
   else  
      cout << "The queue q1 is not greater than "  
           << "the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is not greater than the queue q2.  
The queue q1 is greater than the queue q3.  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 연산자의 좌변에 있는 큐 개체가 우변에 있는 큐 개체보다 크거나 같은지 테스트합니다.  
  
```  
bool operator>=(const queue <Type, Container>& left, const queue <Type, Container>& right,);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 **queue** 형식의 개체입니다.  
  
 ` right`  
 **queue** 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 queue가 연산자 우변의 queue보다 엄격하게 작으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 queue 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소값이 같으면 두 큐는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// queue_op_ge.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2, q3;  
  
   q1.push( 1 );  
   q1.push( 2 );  
   q2.push( 5 );  
   q2.push( 10 );  
   q3.push( 1 );  
   q3.push( 2 );  
  
   if ( q1 >= q2 )  
      cout << "The queue q1 is greater than or equal to "  
           << "the queue q2." << endl;  
   else  
      cout << "The queue q1 is less than "  
           << "the queue q2." << endl;  
  
   if ( q1>= q3 )  
      cout << "The queue q1 is greater than or equal to "  
           << "the queue q3." << endl;  
   else  
      cout << "The queue q1 is less than "  
           << "the queue q3." << endl;  
}  
```  
  
```Output  
The queue q1 is less than the queue q2.  
The queue q1 is greater than or equal to the queue q3.  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<queue>](../standard-library/queue.md)


