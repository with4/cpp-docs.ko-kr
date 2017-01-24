---
title: "stack 클래스 | Microsoft Docs"
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
  - "std::stack"
  - "std.stack"
  - "stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "스택, stack 클래스"
  - "stack 클래스"
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# stack 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

최근에 일부 기본 컨테이너 형식에 추가된 요소로만 액세스를 제한하는 템플릿 컨테이너 어댑터 클래스입니다. stack 클래스는 컨테이너에서 스택 작업만 수행되고 있음을 명확하게 해야 하는 경우에 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Type, class Container= deque <Type>>  
class stack  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Type*  
 스택에 저장되는 요소 데이터 형식입니다.  
  
 `Container`  
 스택을 구현하는 데 사용된 기본 컨테이너의 형식입니다. 기본값은 클래스 `deque`*\< 형식>*합니다.  
  
## <a name="remarks"></a>설명  
 클래스의 요소 **형식** 첫 번째 서식 파일에서 명시한 매개 변수는 스택 개체의 동의어인 [value_type](#stack__value_type) 기본 컨테이너 클래스에 있는 요소의 형식과 일치 해야 **컨테이너** 두 번째 템플릿 매개 변수로 조건으로 규정 합니다.  **형식** 를 해당 형식의 개체를 복사 하 고 해당 형식의 변수에 값을 할당할 수 있도록, 할당할 수 있어야 합니다.  
  
 스택에 대 한 적합 한 기본 컨테이너 클래스에 포함 되어 [e q u e](../standard-library/deque-class.md), [list 클래스](../standard-library/list-class.md), 및 [vector 클래스](../standard-library/vector-class.md), 또는 기타 시퀀스 컨테이너의 작업을 지 원하는 **다시**, `push_back`, 및 `pop_back`합니다. 기본 컨테이너 클래스는 제한된 시퀀스 컨테이너 멤버 함수 집합만 공용 인터페이스로 표시하는 컨테이너 어댑터 내에서 캡슐화되어 있습니다.  
  
 스택 개체 같음 비교 가능한 경우 및 경우에만 클래스의 요소 **형식** 는 같음 비교 가능한 적고 적게-이와 비슷한 if 및 경우에만 보다 클래스의 요소 **형식** 작은-보다 비교할 수입니다.  
  
-   stack 클래스는 LIFO(후입선출) 데이터 구조를 지원합니다. 쌓여 있는 접시 더미의 예로 이해할 수 있습니다. 요소(접시)는 기본 컨테이너의 끝에 있는 마지막 요소인 스택의 맨 위에서만 삽입하거나 검사하거나 제거할 수 있습니다. 맨 위 요소로만 액세스를 제한하는 것이 stack 클래스를 사용하는 이유입니다.  
  
-    [queue 클래스](../standard-library/queue-class.md) 선입 선출 (FIFO) 데이터 구조를 지원 합니다. 은행 창구 직원을 만나려고 줄 서 있는 사람들의 예로 이해할 수 있습니다. 요소(사람)는 줄의 뒤에 추가될 수 있고 줄의 앞에서 제거됩니다. 줄의 앞과 뒤는 모두 검사할 수 있습니다. queue 클래스를 사용하는 이유는 이 방식으로 앞과 뒤의 요소만 액세스할 수 있기 때문입니다.  
  
-    [priority_queue 클래스](../standard-library/priority-queue-class.md) 위쪽 위치에 가장 큰 요소는 항상 되도록 해당 요소를 정렬 합니다. 이 클래스는 요소의 삽입과 최상위 요소의 검사 및 제거를 지원합니다. 나이, 키 또는 기타 조건을 기준으로 정렬된 줄을 선 사람들의 예로 이해할 수 있습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[스택](#stack__stack)|비어 있거나 기본 컨테이너 개체의 복사본인 `stack`을 생성합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[container_type](#stack__container_type)|`stack`에서 조정할 기본 컨테이너를 제공하는 형식입니다.|  
|[size_type](#stack__size_type)|`stack`에서 요소 수를 표현할 수 있는 부호 없는 정수 형식입니다.|  
|[value_type](#stack__value_type)|`stack`에 있는 요소로 저장된 개체의 형식을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[빈](#stack__empty)|`stack`이 비어 있는지를 테스트합니다.|  
|[pop](#stack__pop)|`stack`의 맨 위에 있는 요소를 제거합니다.|  
|[푸시](#stack__push)|`stack`의 맨 위에 요소를 추가합니다.|  
|[크기](#stack__size)|`stack`에 있는 요소 수를 반환합니다.|  
|[맨 위로](#stack__top)|`stack`의 맨 위에 있는 요소에 대한 참조를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 스택>  
  
 **네임스페이스:** std  
  
##  <a name="a-namestackcontainertypea-stackcontainertype"></a><a name="stack__container_type"></a>  stack:: container_type  
 조정 해야 기본 컨테이너를 제공 하는 형식입니다.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Container`의 동의어입니다. 세 STL 시퀀스 컨테이너 클래스는 모두-vector 클래스, list 클래스 및 기본 클래스 deque-스택 개체에 대 한 기본 컨테이너로 사용 될 수 있는 요구 사항을 충족 합니다. 이러한 요구 사항을 만족 하는 사용자 정의 형식 에서도 사용할 수 있습니다.  
  
 대 한 자세한 내용은 `Container`, 의 설명 섹션을 참조는 [stack 클래스](../standard-library/stack-class.md) 항목입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [stack:: stack](#stack__stack) 선언 및 사용 하는 방법의 예에 대 한 `container_type`합니다.  
  
##  <a name="a-namestackemptya-stackempty"></a><a name="stack__empty"></a>  stack:: empty  
 스택이 비어 있는지 테스트 합니다.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 스택이 비어 있으면 **false** 스택은 비어 있지 않은 경우.  
  
### <a name="example"></a>예제  
  
```  
// stack_empty.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack <int> s1, s2;  
  
   s1.push( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The stack s1 is empty." << endl;  
   else  
      cout << "The stack s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The stack s2 is empty." << endl;  
   else  
      cout << "The stack s2 is not empty." << endl;  
}  
```  
  
```Output  
The stack s1 is not empty.  
The stack s2 is empty.  
```  
  
##  <a name="a-namestackpopa-stackpop"></a><a name="stack__pop"></a>  stack:: pop  
 스택의 맨 위에서 요소를 제거 합니다.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>설명  
 스택 멤버 함수를 적용 해야 합니다. 스택의 맨 위에 가장 최근에 추가 된 요소를 차지 하는 위치 이며 컨테이너의 끝에 있는 마지막 요소입니다.  
  
### <a name="example"></a>예제  
  
```  
// stack_pop.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
  
   s1.pop( );  
  
   i = s1.size( );  
   cout << "After a pop, the stack length is "   
        << i << "." << endl;  
  
   i = s1.top( );  
   cout << "After a pop, the element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
After a pop, the stack length is 2.  
After a pop, the element at the top of the stack is 20.  
```  
  
##  <a name="a-namestackpusha-stackpush"></a><a name="stack__push"></a>  stack:: push  
 스택의 맨 위 끝에 요소를 추가 합니다.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
 ` val`  
 요소는 스택의 맨 위에 추가 됩니다.  
  
### <a name="remarks"></a>설명  
 스택의 맨 위에 가장 최근에 추가 된 요소를 차지 하는 위치 이며 컨테이너의 끝에 있는 마지막 요소입니다.  
  
### <a name="example"></a>예제  
  
```  
// stack_push.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
```  
  
##  <a name="a-namestacksizea-stacksize"></a><a name="stack__size"></a>  stack:: size  
 스택에 있는 요소의 수를 반환합니다.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 스택의 현재 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// stack_size.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
   stack <int>::size_type i;  
  
   s1.push( 1 );  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   s1.push( 2 );  
   i = s1.size( );  
   cout << "The stack length is now " << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 1.  
The stack length is now 2.  
```  
  
##  <a name="a-namestacksizetypea-stacksizetype"></a><a name="stack__size_type"></a>  stack:: size_type  
 스택에 있는 요소의 수를 나타낼 수 있는 부호 없는 정수 형식입니다.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>설명  
 에 대 한 동의어를 형식이 `size_type` 스택에 의해 조정 되는 기본 컨테이너입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [크기](#stack__size) 선언 및 사용 하는 방법의 예에 대 한 `size_type`합니다.  
  
##  <a name="a-namestackstacka-stackstack"></a><a name="stack__stack"></a>  stack:: stack  
 스택 하는 비어 있거나 컨테이너를 기본 클래스의 복사본을 생성 합니다.  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 컨테이너 생성 된 스택을 복사본으로입니다.  
  
### <a name="example"></a>예제  
  
```  
// stack_stack.cpp  
// compile with: /EHsc  
#include <stack>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares stack with default deque base container  
   stack <char> dsc1;  
  
   //Explicitly declares a stack with deque base container  
   stack <char, deque<char> > dsc2;  
  
   // Declares a stack with vector base containers  
   stack <int, vector<int> > vsi1;  
  
   // Declares a stack with list base container  
   stack <int, list<int> > lsi;  
  
   // The second member function copies elements from a container  
   vector<int> v1;  
   v1.push_back( 1 );  
   stack <int, vector<int> > vsi2( v1 );  
   cout << "The element at the top of stack vsi2 is "  
        << vsi2.top( ) << "." << endl;  
}  
```  
  
```Output  
The element at the top of stack vsi2 is 1.  
```  
  
##  <a name="a-namestacktopa-stacktop"></a><a name="stack__top"></a>  stack:: top  
 스택의 맨 위에 있는 요소에 대 한 참조를 반환합니다.  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>반환 값  
 스택의 맨 위에 있는 컨테이너의 마지막 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 스택 멤버 함수를 적용 해야 합니다. 스택의 맨 위에 가장 최근에 추가 된 요소를 차지 하는 위치 이며 컨테이너의 끝에 있는 마지막 요소입니다.  
  
 하는 경우의 반환 값 **위쪽** 에 할당 되는 `const_reference`, 스택 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **위쪽** 에 할당 되는 **참조**, 스택 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// stack_top.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 1 );  
   s1.push( 2 );  
  
   int& i = s1.top( );  
   const int& ii = s1.top( );  
  
   cout << "The top integer of the stack s1 is "  
        << i << "." << endl;  
   i--;  
   cout << "The next integer down is "<< ii << "." << endl;  
}  
```  
  
```Output  
The top integer of the stack s1 is 2.  
The next integer down is 1.  
```  
  
##  <a name="a-namestackvaluetypea-stackvaluetype"></a><a name="stack__value_type"></a>  stack:: value_type  
 스택에서 요소로 저장 된 개체의 형식을 나타내는 형식입니다.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>설명  
 에 대 한 동의어를 형식이 `value_type` 스택에 의해 조정 되는 기본 컨테이너입니다.  
  
### <a name="example"></a>예제  
  
```  
// stack_value_type.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   stack<int> s1;  
   s1.push( AnInt );  
   cout << "The element at the top of the stack is "  
        << s1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the stack is 69.  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

