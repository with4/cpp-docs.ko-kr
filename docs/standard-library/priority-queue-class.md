---
title: "priority_queue 클래스 | Microsoft Docs"
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
  - "std.priority_queue"
  - "priority_queue"
  - "std::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue 클래스"
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# priority_queue 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제한의 가장 높은 우선 순위 또는 가장 큰 항상 일부 기본 컨테이너 형식으로의 맨 위에 있는 요소에 대 한 액세스를 제한 하는 기능을 제공 하는 템플릿 컨테이너 어댑터 클래스입니다. priority_queue에 새 요소를 추가할 수 및는 priority_queue 맨 위에 있는 요소를 검사 하거나 제거할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>  
class priority_queue  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Type*  
 priority_queue에 저장 될 요소의 데이터 형식입니다.  
  
 `Container`  
 Priority_queue는를 구현 하는 데 기본 컨테이너의 형식입니다.  
  
 *비교*  
 priority_queue에서 상대적 순서를 결정 하는 정렬 키로 두 요소 값을 비교할 수 있는 함수 개체를 제공 하는 형식입니다. 이 인수는 선택적 이며 이진 조건자 **덜***\<***typename** *컨테이너***:: value_type***>* 기본값입니다.  
  
## <a name="remarks"></a>설명  
 클래스의 요소 **형식** 첫 번째 서식 파일에서 명시한 큐 개체의 매개 변수 동의어인 [value_type](#priority_queue__value_type) 기본 컨테이너 클래스에 있는 요소의 형식과 일치 해야 **컨테이너** 두 번째 템플릿 매개 변수로 조건으로 규정 합니다.  **형식** 를 해당 형식의 개체를 복사 하 고 해당 형식의 변수에 값을 할당할 수 있도록, 할당할 수 있어야 합니다.  
  
 클래스의 저장 된 함수 개체를 호출 하 여 제어 하는 시퀀스를 정렬 하는 priority_queue **특성**합니다. 일반적으로, 이 순서를 정하려면 요소의 크기를 비교할 수 있어야 합니다. 즉, 제공된 어떤 두 요소에서 두 요소가 동일하거나(어떤 것도 다른 것보다 작지 않음) 하나가 다른 것보다 작음을 정할 수 있어야 합니다. 그러면 동일하지 않은 요소 사이에 정렬이 수행됩니다. 기술적으로 설명하면, 비교 함수는 표준 함수의 의미에서 엄밀히 약한 정렬을 수행하는 이진 조건자입니다.  
  
 Priority_queue에 대 한 적합 한 기본 컨테이너 클래스에 포함 되어 [deque 클래스](../standard-library/deque-class.md) 및 기본 [vector 클래스](../standard-library/vector-class.md) 또는 기타 시퀀스 컨테이너의 작업을 지 원하는 `front`, `push_back`, 및 `pop_back` 와 임의 액세스 반복기입니다. 기본 컨테이너 클래스는 제한된 시퀀스 컨테이너 멤버 함수 집합만 공용 인터페이스로 표시하는 컨테이너 어댑터 내에서 캡슐화되어 있습니다.  
  
 요소를 추가 하 고 요소를 제거는 `priority_queue` 로그 복잡성을 갖추고 있습니다. 요소에 액세스 한 `priority_queue` 고정적 복잡성이 있습니다.  
  
 컨테이너 어댑터는 STL에 정의 된 세 가지 종류가 있습니다: 스택, 큐 및 priority_queue 합니다. 각 표준 데이터 구조를 정확 하 게 제어 된 인터페이스를 제공 하도록 몇 가지 기본 컨테이너 클래스의 기능을 제한 합니다.  
  
-    [stack 클래스](../standard-library/stack-class.md) 마지막에 lifo (후입선출) 데이터 구조를 지원 합니다. 쌓여 있는 접시 더미의 예로 이해할 수 있습니다. 요소(접시)는 기본 컨테이너의 끝에 있는 마지막 요소인 스택의 맨 위에서만 삽입하거나 검사하거나 제거할 수 있습니다. 맨 위 요소로만 액세스를 제한하는 것이 stack 클래스를 사용하는 이유입니다.  
  
-    [queue 클래스](../standard-library/queue-class.md) 선입 선출 (FIFO) 데이터 구조를 지원 합니다. 은행 창구 직원을 만나려고 줄 서 있는 사람들의 예로 이해할 수 있습니다. 요소(사람)는 줄의 뒤에 추가될 수 있고 줄의 앞에서 제거됩니다. 줄의 앞과 뒤는 모두 검사할 수 있습니다. 이러한 방식으로 프런트 엔드와 백 요소에 액세스 하는 제한이 큐 클래스를 사용 하는 이유입니다.  
  
-   Priority_queue 클래스 위쪽 위치에 가장 큰 요소는 항상 되도록 해당 요소를 정렬 합니다. 이 클래스는 요소의 삽입과 최상위 요소의 검사 및 제거를 지원합니다. 나이, 키 또는 기타 조건을 기준으로 정렬된 줄을 선 사람들의 예로 이해할 수 있습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[priority_queue](#priority_queue__priority_queue)|생성 된 `priority_queue` 비어 있거나 하가 기본 컨테이너 개체 또는 다른 범위의 복사본 `priority_queue`합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[container_type](#priority_queue__container_type)|`priority_queue`에서 조정할 기본 컨테이너를 제공하는 형식입니다.|  
|[size_type](#priority_queue__size_type)|`priority_queue`에서 요소 수를 표현할 수 있는 부호 없는 정수 형식입니다.|  
|[value_type](#priority_queue__value_type)|`priority_queue`에 있는 요소로 저장된 개체의 형식을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[빈](#priority_queue__empty)|`priority_queue`이 비어 있는지를 테스트합니다.|  
|[pop](#priority_queue__pop)|가장 큰 요소를 제거는 `priority_queue` 맨 위에서 다른 위치로 합니다.|  
|[푸시](#priority_queue__push)|요소 연산자의 우선 순위에 따라 우선 순위 큐에 요소를 추가 <.|  
|[크기](#priority_queue__size)|`priority_queue`에 있는 요소 수를 반환합니다.|  
|[맨 위로](#priority_queue__top)|반환 대 한 const 참조 맨 위에 있는 가장 큰 요소는 `priority_queue`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 큐>  
  
 **네임스페이스:** std  
  
##  <a name="a-namepriorityqueuecontainertypea-priorityqueuecontainertype"></a><a name="priority_queue__container_type"></a>  priority_queue:: container_type  
 조정 해야 기본 컨테이너를 제공 하는 형식입니다.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Container`의 동의어입니다. 기본 클래스 벡터 및 STL 시퀀스 컨테이너 클래스 deque priority_queue 개체에 대 한 기본 컨테이너로 사용 될 수 있는 요구 사항을 충족 합니다. 사용자 정의 형식 요구 사항에 맞는 사용할 수도 있습니다.  
  
 대 한 자세한 내용은 `Container`, 의 설명 섹션을 참조는 [priority_queue 클래스](../standard-library/priority-queue-class.md) 항목입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [priority_queue](#priority_queue__priority_queue) 선언 및 사용 하는 방법의 예에 대 한 `container_type`합니다.  
  
##  <a name="a-namepriorityqueueemptya-priorityqueueempty"></a><a name="priority_queue__empty"></a>  priority_queue:: empty  
 Priority_queue는 비어 있는 경우를 테스트 합니다.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 는 priority_queue 비어 있는 경우 **false** 는 priority_queue 비어 있지 않은 경우.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue <int> q1, s2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The priority_queue q1 is empty." << endl;  
   else  
      cout << "The priority_queue q1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The priority_queue s2 is empty." << endl;  
   else  
      cout << "The priority_queue s2 is not empty." << endl;  
}  
```  
  
```Output  
The priority_queue q1 is not empty.  
The priority_queue s2 is empty.  
```  
  
##  <a name="a-namepriorityqueuepopa-priorityqueuepop"></a><a name="priority_queue__pop"></a>  priority_queue:: pop  
 위쪽 위치에서는 priority_queue의 가장 큰 요소를 제거합니다.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>설명  
 멤버 함수를 적용하려면 priority_queue는 비어 있지 않아야 합니다. priority_queue의 맨 위에 가장 큰 요소는 컨테이너에 항상 차지 합니다.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   priority_queue <int>::size_type i, iii;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
  
   q1.pop( );  
  
   iii = q1.size( );  
   cout << "After a pop, the priority_queue length is "   
        << iii << "." << endl;  
  
   const int& iv = q1.top( );  
   cout << "After a pop, the element at the top of the "  
        << "priority_queue is " << iv << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
After a pop, the priority_queue length is 2.  
After a pop, the element at the top of the priority_queue is 20.  
```  
  
##  <a name="a-namepriorityqueuepriorityqueuea-priorityqueuepriorityqueue"></a><a name="priority_queue__priority_queue"></a>  priority_queue:: priority_queue  
 비어 있거나 다른 priority_queue 또는 기본 컨테이너 개체의 범위의 복사본 priority_queue를 생성 합니다.  
  
```  
priority_queue();

explicit priority_queue(const Traits&_comp);

priority_queue(const Traits&_comp, const container_type& _Cont);

priority_queue(const priority_queue& right);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp, const container_type& _Cont);
```  
  
### <a name="parameters"></a>매개 변수  
 *_-설치 완료*  
 형식의 비교 함수 **constTraits** 는 기본적으로 기본 컨테이너의 함수를 비교 하도록 priority_queue에 요소를 정렬 하는 데 사용 합니다.  
  
 `_Cont`  
 복사본으로 생성 된 priority_queue는 포함 하는 기본 컨테이너입니다.  
  
 ` right`  
 복사본으로 생성 된 집합은 priority_queue 합니다.  
  
 ` first`  
 복사할 요소의 범위에서 첫 번째 요소의 위치입니다.  
  
 ` last`  
 복사할 요소의 범위를 벗어나는 첫 번째 요소의 위치입니다.  
  
### <a name="remarks"></a>설명  
 처음 세 명의 생성자 중 각각 두 번째도 지정 하는 비교 함수는 빈 초기 priority_queue 지정 ( ` comp`) 요소 및 세 번째 명시적으로 지정 하는 순서를 설정 하는 데 사용 되는 `container_type` ( `_Cont`) 사용할 수 있습니다. 키워드 **명시적** 특정 종류의 자동 형식 변환 표시 하지 않습니다.  
  
 priority_queue의 복사본을 지정 하는 네 번째 생성자는 ` right`합니다.  
  
 범위를 복사 하는 마지막 세 명의 생성자 [ * 이름, 성*) 일부 컨테이너의 값을 사용 하는 클래스의 비교 함수의 유형을 지정 하는 명시적인 증가 priority_queue 초기화 **특성** 및 `container_type`합니다.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_ctor.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <deque>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function declares priority_queue  
   // with a default vector base container  
   priority_queue <int> q1;  
   cout << "q1 = ( ";  
   while ( !q1.empty( ) )  
   {  
      cout << q1.top( ) << " ";  
      q1.pop( );  
   }  
   cout << ")" << endl;  
  
   // Explicitly declares a priority_queue with nondefault  
   // deque base container  
   priority_queue <int, deque <int> > q2;  
   q2.push( 5 );  
   q2.push( 15 );  
   q2.push( 10 );  
   cout << "q2 = ( ";  
   while ( !q2.empty( ) )  
   {  
      cout << q2.top( ) << " ";  
      q2.pop( );  
   }  
   cout << ")" << endl;  
  
   // This method of printing out the elements of a priority_queue  
   // removes the elements from the priority queue, leaving it empty  
   cout << "After printing, q2 has " << q2.size( ) << " elements." << endl;  
  
   // The third member function declares a priority_queue   
   // with a vector base container and specifies that the comparison   
   // function greater is to be used for ordering elements  
   priority_queue <int, vector<int>, greater<int> > q3;  
   q3.push( 2 );  
   q3.push( 1 );  
   q3.push( 3 );  
   cout << "q3 = ( ";  
   while ( !q3.empty( ) )  
   {  
      cout << q3.top( ) << " ";  
      q3.pop( );  
   }  
   cout << ")" << endl;  
  
   // The fourth member function declares a priority_queue and  
   // initializes it with elements copied from another container:  
   // first, inserting elements into q1, then copying q1 elements into q4  
   q1.push( 100 );  
   q1.push( 200 );  
   priority_queue <int> q4( q1 );  
   cout << "q4 = ( ";     
   while ( !q4.empty( ) )  
   {  
      cout << q4.top( ) << " ";  
      q4.pop( );  
   }  
   cout << ")" << endl;  
  
   // Creates an auxiliary vector object v5 to be used to initialize q5  
   vector <int> v5;  
   vector <int>::iterator v5_Iter;  
   v5.push_back( 10 );  
   v5.push_back( 30 );  
   v5.push_back( 20 );  
   cout << "v5 = ( " ;  
   for ( v5_Iter = v5.begin( ) ; v5_Iter != v5.end( ) ; v5_Iter++ )  
      cout << *v5_Iter << " ";  
   cout << ")" << endl;  
  
   // The fifth member function declares and  
   // initializes a priority_queue q5 by copying the  
   // range v5[ first,  last) from vector v5  
   priority_queue <int> q5( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q5 = ( ";  
   while ( !q5.empty( ) )  
   {  
      cout << q5.top( ) << " ";  
      q5.pop( );  
   }  
   cout << ")" << endl;  
  
   // The sixth member function declares a priority_queue q6  
   // with a comparison function greater and initializes q6  
   // by copying the range v5[ first,  last) from vector v5  
   priority_queue <int, vector<int>, greater<int> >   
      q6( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q6 = ( ";  
   while ( !q6.empty( ) )  
   {  
      cout << q6.top( ) << " ";  
      q6.pop( );  
   }  
   cout << ")" << endl;  
}  
```  
  
##  <a name="a-namepriorityqueuepusha-priorityqueuepush"></a><a name="priority_queue__push"></a>  priority_queue:: push  
 요소 연산자의 우선 순위에 따라 우선 순위 큐에 요소를 추가 <.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
 ` val`  
 priority_queue의 맨 위에 추가 하는 요소입니다.  
  
### <a name="remarks"></a>설명  
 priority_queue의 맨 위에 컨테이너의 가장 큰 요소를 차지 하는 위치입니다.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuesizea-priorityqueuesize"></a><a name="priority_queue__size"></a>  priority_queue:: size  
 priority_queue의 요소 수를 반환합니다.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 priority_queue의 현재 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, q2;  
   priority_queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The priority_queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 1.  
The priority_queue length is now 2.  
```  
  
##  <a name="a-namepriorityqueuesizetypea-priorityqueuesizetype"></a><a name="priority_queue__size_type"></a>  priority_queue:: size_type  
 priority_queue에 있는 요소의 수를 나타낼 수 있는 부호 없는 정수 형식입니다.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>설명  
 형식이 대 한 동의어는 `size_type` 는 priority_queue로 조정 하는 기본 컨테이너입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [크기](#priority_queue__size) 선언 및 사용 하는 방법의 예에 대 한 `size_type`합니다.  
  
##  <a name="a-namepriorityqueuetopa-priorityqueuetop"></a><a name="priority_queue__top"></a>  priority_queue:: top  
 가장 큰 요소에 대한 const 참조를 priority_queue 위쪽에 반환합니다.  
  
```  
const_reference top() const;
```  
  
### <a name="return-value"></a>반환 값  
 기준으로 가장 큰 요소에 대 한 참조는 **특성** 함수, 개체는 priority_queue입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수를 적용하려면 priority_queue는 비어 있지 않아야 합니다.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_top.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuevaluetypea-priorityqueuevaluetype"></a><a name="priority_queue__value_type"></a>  priority_queue:: value_type  
 priority_queue의 요소로 저장 된 개체의 형식을 나타내는 형식입니다.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>설명  
 형식이 대 한 동의어는 `value_type` 는 priority_queue로 조정 하는 기본 컨테이너입니다.  
  
### <a name="example"></a>예제  
  
```  
// pqueue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   priority_queue<int> q1;  
   q1.push( AnInt );  
   cout << "The element at the top of the priority_queue is "  
        << q1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the priority_queue is 69.  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

