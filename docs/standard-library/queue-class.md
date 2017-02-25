---
title: "queue 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.queue"
  - "std::queue"
  - "queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue 클래스"
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# queue 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프런트 엔드와 백 요소에 대 한 액세스를 제한 합니다. 일부 기본 컨테이너 형식에 대 한 제한 기능을 제공 하는 템플릿 컨테이너 어댑터 클래스입니다. 요소 뒤에 추가 하거나, 앞에서 제거할 수 및 큐의 끝에 요소를 검사할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Type, class Container = deque <Type>>  
class queue  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Type*  
 큐에 저장 될 요소의 데이터 형식  
  
 `Container`  
 큐를 구현 하는 데 기본 컨테이너의 형식입니다.  
  
## <a name="remarks"></a>설명  
 클래스의 요소 **형식** 첫 번째 서식 파일에서 명시한 큐 개체의 매개 변수 동의어인 [value_type](#queue__value_type) 기본 컨테이너 클래스에 있는 요소의 형식과 일치 해야 **컨테이너** 두 번째 템플릿 매개 변수로 조건으로 규정 합니다.  **형식** 를 해당 형식의 개체를 복사 하 고 해당 형식의 변수에 값을 할당할 수 있도록, 할당할 수 있어야 합니다.  
  
 큐에 대 한 적합 한 기본 컨테이너 클래스에 포함 되어 [e q u e](../standard-library/deque-class.md) 및 [목록](../standard-library/list-class.md), 또는 기타 시퀀스 컨테이너의 작업을 지 원하는 `front`, **다시**, `push_back`, 및 `pop_front`합니다. 기본 컨테이너 클래스는 제한된 시퀀스 컨테이너 멤버 함수 집합만 공용 인터페이스로 표시하는 컨테이너 어댑터 내에서 캡슐화되어 있습니다.  
  
 큐 개체 같음 비교 가능한 경우 및 경우에만 클래스의 요소 **형식** 는 같음 비교 및 작은-비교 가능한 경우 및 경우에만 보다 클래스의 요소 **형식** 작은-보다 비교할 수입니다.  
  
 컨테이너 어댑터는 STL에 정의 된 세 가지 종류가 있습니다: 스택, 큐 및 priority_queue 합니다. 각 표준 데이터 구조를 정확 하 게 제어 된 인터페이스를 제공 하도록 몇 가지 기본 컨테이너 클래스의 기능을 제한 합니다.  
  
-    [stack 클래스](../standard-library/stack-class.md) 마지막에 lifo (후입선출) 데이터 구조를 지원 합니다. 쌓여 있는 접시 더미의 예로 이해할 수 있습니다. 요소(접시)는 기본 컨테이너의 끝에 있는 마지막 요소인 스택의 맨 위에서만 삽입하거나 검사하거나 제거할 수 있습니다. 맨 위 요소로만 액세스를 제한하는 것이 stack 클래스를 사용하는 이유입니다.  
  
-   큐 클래스는 선입 선출 (FIFO) 데이터 구조를 지원합니다. 은행 창구 직원을 만나려고 줄 서 있는 사람들의 예로 이해할 수 있습니다. 요소(사람)는 줄의 뒤에 추가될 수 있고 줄의 앞에서 제거됩니다. 줄의 앞과 뒤는 모두 검사할 수 있습니다. 이러한 방식으로 프런트 엔드와 백 요소에 액세스 하는 제한이 큐 클래스를 사용 하는 이유입니다.  
  
-    [priority_queue 클래스](../standard-library/priority-queue-class.md) 위쪽 위치에 가장 큰 요소는 항상 되도록 해당 요소를 정렬 합니다. 이 클래스는 요소의 삽입과 최상위 요소의 검사 및 제거를 지원합니다. 나이, 키 또는 기타 조건을 기준으로 정렬된 줄을 선 사람들의 예로 이해할 수 있습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[큐](#queue__queue)|비어 있거나 기본 컨테이너 개체의 복사본인 `queue`을 생성합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[container_type](#queue__container_type)|기본 컨테이너에서 조정할 수를 제공 하는 형식에서 `queue`합니다.|  
|[size_type](#queue__size_type)|`queue`에서 요소 수를 표현할 수 있는 부호 없는 정수 형식입니다.|  
|[value_type](#queue__value_type)|`queue`에 있는 요소로 저장된 개체의 형식을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[뒤로](#queue__back)|참조를 마지막 및 가장 최근에 추가 요소는 뒤쪽에 반환 된 `queue`합니다.|  
|[빈](#queue__empty)|`queue`이 비어 있는지를 테스트합니다.|  
|[앞면](#queue__front)|앞에 첫 번째 요소에 대 한 참조를 반환 된 `queue`합니다.|  
|[pop](#queue__pop)|앞에서 요소를 제거는 `queue`합니다.|  
|[푸시](#queue__push)|맨 뒤로 요소를 추가 `queue`합니다.|  
|[크기](#queue__size)|`queue`에 있는 요소 수를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 큐>  
  
 **네임스페이스:** std  
  
##  <a name="a-namequeuebacka-queueback"></a><a name="queue__back"></a>  queue:: back  
 참조를 마지막 및 가장 최근에 추가 큐 뒤에 있는 요소를 반환 합니다.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>반환 값  
 큐의 마지막 요소입니다. 큐가 비어 있으면 반환 값은 정의 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 **다시** 에 할당 되는 `const_reference`, 큐 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **다시** 에 할당 되는 **참조**, 큐 개체를 수정할 수 있습니다.  
  
 _SECURE_SCL 1 컴파일할 때 빈 큐에 있는 요소에 액세스 하려고 하면 런타임 오류가 발생 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// queue_back.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 11 );  
  
   int& i = q1.back( );  
   const int& ii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << i   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << ii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuecontainertypea-queuecontainertype"></a><a name="queue__container_type"></a>  queue:: container_type  
 조정 해야 기본 컨테이너를 제공 하는 형식입니다.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Container`의 동의어입니다. 두 STL 시퀀스 컨테이너 클래스-list 클래스 및 기본 deque 클래스-큐 개체에 대 한 기본 컨테이너로 사용 될 수 있는 요구 사항을 충족 합니다. 사용자 정의 형식 요구 사항에 맞는 사용할 수도 있습니다.  
  
 대 한 자세한 내용은 `Container`, 의 설명 섹션을 참조는 [queue 클래스](../standard-library/queue-class.md) 항목입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [큐](#queue__queue) 선언 및 사용 하는 방법의 예에 대 한 `container_type`합니다.  
  
##  <a name="a-namequeueemptya-queueempty"></a><a name="queue__empty"></a>  queue:: empty  
 큐가 비어 있는지 테스트 합니다.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 큐가 비어 있으면 **false** 큐가 비어 있지 않은 경우.  
  
### <a name="example"></a>예제  
  
```  
// queue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The queue q1 is empty." << endl;  
   else  
      cout << "The queue q1 is not empty." << endl;  
  
   if ( q2.empty( ) )  
      cout << "The queue q2 is empty." << endl;  
   else  
      cout << "The queue q2 is not empty." << endl;  
}  
```  
  
```Output  
The queue q1 is not empty.  
The queue q2 is empty.  
```  
  
##  <a name="a-namequeuefronta-queuefront"></a><a name="queue__front"></a>  queue:: front  
 큐의 앞에 있는 첫 번째 요소에 대 한 참조를 반환합니다.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>반환 값  
 큐의 첫 번째 요소입니다. 큐가 비어 있으면 반환 값은 정의 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 `front` 에 할당 되는 `const_reference`, 큐 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `front` 에 할당 되는 **참조**, 큐 개체를 수정할 수 있습니다.  
  
 멤버 함수가 반환 하는 **참조** 제어 된 시퀀스의 첫 번째 요소에 비워 둘 수 있습니다.  
  
 _SECURE_SCL 1 컴파일할 때 빈 큐에 있는 요소에 액세스 하려고 하면 런타임 오류가 발생 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// queue_front.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   int& ii = q1.back( );  
   int& iii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << ii   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << iii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuepopa-queuepop"></a><a name="queue__pop"></a>  queue:: pop  
 큐의 앞에서 요소를 제거합니다.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>설명  
 큐 멤버 함수를 적용 해야 합니다. 큐의 맨 위에 가장 최근에 추가 된 요소를 차지 하는 위치 이며 컨테이너의 끝에 있는 마지막 요소입니다.  
  
### <a name="example"></a>예제  
  
```  
// queue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
  
   q1.pop( );  
  
   i = q1.size( );  
   cout << "After a pop the queue length is "   
        << i << "." << endl;  
  
   i = q1. front ( );  
   cout << "After a pop, the element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
After a pop the queue length is 2.  
After a pop, the element at the front of the queue is 20.  
```  
  
##  <a name="a-namequeuepusha-queuepush"></a><a name="queue__push"></a>  queue:: push  
 큐의 맨 뒤로 요소를 추가 합니다.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `val`  
 큐의 맨 뒤에 추가 하는 요소입니다.  
  
### <a name="remarks"></a>설명  
 큐의 뒷면 가장 최근에 추가 된 요소를 차지 하는 위치 이며 컨테이너의 끝에 있는 마지막 요소입니다.  
  
### <a name="example"></a>예제  
  
```  
// queue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
```  
  
##  <a name="a-namequeuequeuea-queuequeue"></a><a name="queue__queue"></a>  queue:: queue  
 기본 컨테이너 개체의 복사본 또는 비어 있는 큐를 생성 합니다.  
  
```  
queue();

explicit queue(const container_type& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
  **const** 컨테이너는 생성 된 큐를 복사본으로입니다.  
  
### <a name="remarks"></a>설명  
 큐에 대 한 기본 기본 컨테이너에는 deque입니다. 기본 컨테이너 목록도 지정할 수 있습니다 있지만 필수 없기 때문에 벡터를 지정할 수 없습니다 `pop_front` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  
```  
// queue_queue.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queue with default deque base container  
   queue <char> q1;  
  
   // Explicitly declares a queue with deque base container  
   queue <char, deque<char> > q2;  
  
   // These lines don't cause an error, even though they  
   // declares a queue with a vector base container  
   queue <int, vector<int> > q3;  
   q3.push( 10 );  
   // but the following would cause an error because vector has   
   // no pop_front member function  
   // q3.pop( );  
  
   // Declares a queue with list base container  
   queue <int, list<int> > q4;  
  
   // The second member function copies elements from a container  
   list<int> li1;  
   li1.push_back( 1 );  
   li1.push_back( 2 );  
   queue <int, list<int> > q5( li1 );  
   cout << "The element at the front of queue q5 is "  
        << q5.front( ) << "." << endl;  
   cout << "The element at the back of queue q5 is "  
        << q5.back( ) << "." << endl;  
}  
```  
  
```Output  
The element at the front of queue q5 is 1.  
The element at the back of queue q5 is 2.  
```  
  
##  <a name="a-namequeuesizea-queuesize"></a><a name="queue__size"></a>  queue:: size  
 큐에 있는 요소의 수를 반환합니다.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 큐의 현재 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// queue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2;  
   queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 1.  
The queue length is now 2.  
```  
  
##  <a name="a-namequeuesizetypea-queuesizetype"></a><a name="queue__size_type"></a>  queue:: size_type  
 큐에 있는 요소의 수를 나타낼 수 있는 부호 없는 정수 형식입니다.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>설명  
 형식이 대 한 동의어는 `size_type` 큐에서 조정 하는 기본 컨테이너입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [queue:: front](#queue__front) 선언 및 사용 하는 방법의 예에 대 한 `size_type`합니다.  
  
##  <a name="a-namequeuevaluetypea-queuevaluetype"></a><a name="queue__value_type"></a>  queue:: value_type  
 큐에 있는 요소로 저장 된 개체의 형식을 나타내는 형식입니다.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>설명  
 형식이 대 한 동의어는 `value_type` 큐에서 조정 하는 기본 컨테이너입니다.  
  
### <a name="example"></a>예제  
  
```  
// queue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   queue<int> q1;  
   q1.push(AnInt);  
   cout << "The element at the front of the queue is "  
        << q1.front( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the front of the queue is 69.  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

