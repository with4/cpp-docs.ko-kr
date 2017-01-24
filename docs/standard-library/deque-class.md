---
title: "deque 클래스 | Microsoft Docs"
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
  - "std.deque"
  - "deque"
  - "std::deque"
  - "deque/std::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "deque 클래스에 대 한 deque 클래스"
  - "deque 클래스"
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# deque 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

선형 정렬에서 지정된 형식의 요소를 정렬하고 벡터처럼 모든 요소에 대한 빠른 임의 액세스와 컨테이너 뒤쪽에서 효율적인 삽입 및 삭제를 가능하게 합니다. 그러나 벡터와 달리 `deque` 클래스는 컨테이너 앞에서 효율적인 삽입 및 삭제를 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```unstlib  
template <class Type,   
    class Allocator =allocator<Type>>  
class deque  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Type`  
 deque에 저장되는 요소 데이터 형식입니다.  
  
 `Allocator`  
 deque의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항 및 기본값은 **할당자 \< 형식>***합니다.*  
  
## <a name="remarks"></a>설명  
 컨테이너 형식은 일반적으로 응용 프로그램에서 필요한 검색과 삽입의 형식을 기준으로 선택해야 합니다. [벡터](../standard-library/vector-class.md) 요소에 대 한 임의 액세스 가장 중요할 및 삽입 또는 삭제 요소의 시퀀스를 관리 하기 위한 기본 컨테이너로 사용 해야 시퀀스의 끝에 사용 해야 합니다. 목록 컨테이너의 성능이 뛰어난 효율적인 경우 삽입은 및 시퀀스 내 모든 위치에서 삭제 (일정 시간)에 중요할 수 있습니다. 시퀀스 중 이러한 작업에는 시퀀스의 요소 수에 비례하는 요소 복사본 및 할당이 필요합니다(선형 시간).  
  
 멤버 함수가 시퀀스의 요소를 삽입하거나 지워야 하면 deque 다시 할당이 수행됩니다.  
  
-   요소는 빈 시퀀스를 삽입 또는 빈 시퀀스를 요소 지워지면 하는 경우 다음 반복기 이전 반환 하 여 [시작](#deque__begin) 및 [끝](#deque__end) 유효 하지 않게 합니다.  
  
-   deque의 첫 번째 위치에 요소를 삽입하는 경우 기존 요소를 지정하는 모든 반복기가 무효화되지만 참조는 그렇지 않습니다.  
  
-   요소는 deque의 끝에 다음 삽입 됩니다 [끝](#deque__end) 및 모든 반복기 있지만 유효 하지 않게 하는 기존 요소를 지정 하는 참조 하십시오.  
  
-   deque 앞에서 요소를 지우는 경우 해당 반복기와 지워진 요소에 대한 참조만 무효화됩니다.  
  
-   deque의 끝에서 마지막 요소를 지우는 경우 최종 요소에 대한 해당 반복기와 지워진 요소에 대한 참조만 무효화됩니다.  
  
 그렇지 않으면 요소를 삽입 또는 제거하는 경우 모든 반복기와 참조가 무효화됩니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[q u e](#deque__deque)|생성 한 `deque.` 새 콘텐츠를 설정 하려면 몇 가지 생성자 제공 됩니다 `deque` 다양 한 방식에서: 빈; 지정된 된 수의 비어 있는 요소와 함께 로드, 이동 또는 복사 된에서 다른 콘텐츠 `deque`; 내용을 복사 하거나, 사용 하는 반복기를 사용 하 여 이동 하 고 하나의 요소에 복사는 `deque`` count` 시간. 일부 생성자의 경우 사용자 지정 `allocator`를 사용하여 요소를 만들 수 있습니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[allocator_type](#deque__allocator_type)|`allocator` 개체의 `deque` 클래스를 나타내는 형식입니다.|  
|[const_iterator](#deque__const_iterator)|`deque`의 요소를 `const`로 액세스하고 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[const_pointer](#deque__const_pointer)|`deque`의 요소에 대한 포인터를 `const.`로 제공하는 형식입니다.|  
|[const_reference](#deque__const_reference)|읽기 및 기타 작업을 위해 `deque`의 요소에 대한 참조를 `const.`로 제공하는 형식입니다.|  
|[const_reverse_iterator](#deque__const_reverse_iterator)|`deque`의 요소를 `const`로 액세스하고 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다. deque가 역방향으로 표시됩니다. 자세한 내용은 참조 [reverse_iterator 클래스](../standard-library/reverse-iterator-class.md)|  
|[difference_type](#deque__difference_type)|동일한 `deque` 내의 요소를 참조하는 두 임의 액세스 반복기 간의 차이를 제공하는 형식입니다.|  
|[반복기](#deque__iterator)|`deque`에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[포인터](#deque__pointer)|`deque`의 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](#deque__reference)|`deque` 내에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|[reverse_iterator](#deque__reverse_iterator)|`deque`에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다. deque가 역방향으로 표시됩니다.|  
|[size_type](#deque__size_type)|`deque`의 요소 수를 계산하는 형식입니다.|  
|[value_type](#deque__value_type)|`deque` 내에 저장된 데이터 형식을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[할당](#deque__assign)|`deque`에서 요소를 지우고 대상 `deque`에 요소의 새 시퀀스를 복사합니다.|  
|[에서](#deque__at)|`deque`의 지정된 위치에 있는 요소에 대한 참조를 반환합니다.|  
|[뒤로](#deque__back)|`deque`의 마지막 요소에 대한 참조를 반환합니다.|  
|[시작](#deque__begin)|`deque`의 첫 번째 요소를 처리하는 임의 액세스 반복기를 반환합니다.|  
|[deque:: cbegin](#deque__cbegin)|`deque`의 첫 번째 요소에 대해 const 반복기를 반환합니다.|  
|[deque:: cend](#deque__cend)|`deque` 끝의 바로 다음을 가리키는 임의 액세스 `const` 반복기를 반환합니다.|  
|[지우기](#deque__clear)|`deque`의 모든 요소를 지웁니다.|  
|[deque:: crbegin](#deque__crbegin)|역방향으로 표시된 `deque`의 첫 번째 요소에 대한 임의 액세스 const 반복기를 반환합니다.|  
|[deque:: crend](#deque__crend)|역방향으로 표시된 `deque`의 첫 번째 요소에 대한 임의 액세스 const 반복기를 반환합니다.|  
|[deque:: emplace](#deque__emplace)|내부에서 생성된 요소를 `deque`의 지정된 위치에 삽입합니다.|  
|[deque:: emplace_back](#deque__emplace_back)|생성된 요소를 `deque`의 끝에 추가합니다.|  
|[deque:: emplace_front](#deque__emplace_front)|생성된 요소를 `deque`의 시작 부분에 추가합니다.|  
|[빈](#deque__empty)|`deque`에 0개의 요소가 포함된 경우 `true`를 반환하고, 하나 이상의 요소가 포함된 경우 `false`를 반환합니다.|  
|[끝](#deque__end)|`deque` 끝의 바로 다음을 가리키는 임의 액세스 반복기를 반환합니다.|  
|[지우기](#deque__erase)|`deque`의 지정된 위치에서 요소 또는 요소 범위를 제거합니다.|  
|[앞면](#deque__front)|`deque`의 첫 번째 요소에 대한 참조를 반환합니다.|  
|[get_allocator](#deque__get_allocator)|`allocator`를 생성하는 데 사용된 `deque` 개체의 복사본을 반환합니다.|  
|[삽입](#deque__insert)|한 요소, 여러 요소 또는 요소의 범위를 `deque`의 지정된 위치에 삽입합니다.|  
|[max_size](#deque__max_size)|`deque`의 최대 허용 길이를 반환합니다.|  
|[pop_back](#deque__pop_back)|`deque`의 끝에 있는 요소를 지웁니다.|  
|[pop_front](#deque__pop_front)|`deque`의 시작 부분에 있는 요소를 지웁니다.|  
|[push_back](#deque__push_back)|`deque`의 끝에 요소를 추가합니다.|  
|[push_front](#deque__push_front)|`deque`의 시작 부분에 요소를 추가합니다.|  
|[rbegin](#deque__rbegin)|역방향 `deque`의 첫 번째 요소에 대한 임의 액세스 반복기를 반환합니다.|  
|[rend](#deque__rend)|역방향 `deque`에서 마지막 요소 바로 다음을 가리키는 임의 액세스 반복기를 반환합니다.|  
|[크기 조정](#deque__resize)|`deque`의 새 크기를 지정합니다.|  
|[deque:: shrink_to_fit](#deque__shrink_to_fit)|여분의 용량을 삭제합니다.|  
|[크기](#deque__size)|`deque`에 있는 요소 수를 반환합니다.|  
|[스왑](#deque__swap)|두 `deque`의 요소를 교환합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 &#91; &#93;](#deque__operator_at)|지정된 위치에 있는 `deque` 요소에 대한 참조를 반환합니다.|  
|[deque:: operator =](#deque__operator_eq)|`deque`의 요소를 다른 `deque`의 복사본으로 바꿉니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \< e q u e>  
  
##  <a name="a-namedequeallocatortypea-dequeallocatortype"></a><a name="deque__allocator_type"></a>  deque:: allocator_type  
 Deque 개체에 대 한 할당자 클래스를 나타내는 형식입니다.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>설명  
 **allocator_type** 템플릿 매개 변수는 동의어 **할당자**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [get_allocator](#deque__get_allocator)합니다.  
  
##  <a name="a-namedequeassigna-dequeassign"></a><a name="deque__assign"></a>  deque:: assign  
 q u e에서 요소를 삭제 하 고 대상 deque에 요소의 새 집합을 복사 합니다.  
  
```  
template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);

void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>매개 변수  
 `First`  
 인수 deque에서 복사할 요소의 범위에서 첫 번째 요소의 위치입니다.  
  
 `Last`  
 인수 deque에서 복사할 요소의 범위를 벗어나는 첫 번째 요소의 위치입니다.  
  
 `Count`  
 에 deque 삽입 되는 요소의 복사본의 수입니다.  
  
 `Val`  
 q u e에 삽입 되는 요소의 값입니다.  
  
 `IList`  
 에 deque 삽입 되는 initializer_list입니다.  
  
### <a name="remarks"></a>설명  
 대상 deque에서 기존 요소는 삭제 후 `assign` 대상 deque에 원래 deque 또는 일부 다른 e q u e에서 지정된 된 범위의 요소를 삽입 하거나 대상 deque에 지정된 된 값의 새 요소 복사본을 삽입 합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_assign.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <initializer_list>  
  
int main()  
{  
    using namespace std;  
    deque <int> c1, c2;  
    deque <int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    deque<int> d1{ 1, 2, 3, 4 };  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    d1.assign(iList);  
  
    cout << "d1 = ";  
    for (int i : d1)  
        cout << i;  
    cout << endl;  
  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
}  
  
```  
  
```Output  
d1 = 5678c1 =102030c1 =5060c1 =4444444  
```  
  
##  <a name="a-namedequeata-dequeat"></a><a name="deque__at"></a>  deque:: at  
 q u e에 지정된 된 위치에 있는 요소에 대 한 참조를 반환합니다.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Pos`  
 아래 첨자 또는 위치 번호 요소는 q u e에서 참조할.  
  
### <a name="return-value"></a>반환 값  
 경우 `_Pos` 는 deque의 크기 보다 크면 **에서** 예외를 throw 합니다.  
  
### <a name="return-value"></a>반환 값  
 하는 경우의 반환 값 **에서** 에 할당 되는 `const_reference`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **에서** 에 할당 되는 **참조**, e q u e 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_at.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int& i = c1.at( 0 );  
   int& j = c1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequebacka-dequeback"></a><a name="deque__back"></a>  deque:: back  
 q u e의 마지막 요소에 대 한 참조를 반환합니다.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>반환 값  
 마지막 요소는 q u e입니다. Deque는 비어 있는 경우 반환 값은 정의 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 **다시** 에 할당 되는 `const_reference`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **다시** 에 할당 되는 **참조**, e q u e 개체를 수정할 수 있습니다.  
  
 _SECURE_SCL 1 컴파일하는 경우 요소는 빈 deque에 액세스 하려고 하면 런타임 오류가 발생 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// deque_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="a-namedequebegina-dequebegin"></a><a name="deque__begin"></a>  deque:: begin  
 q u e의 첫 번째 요소를 가리키는 반복기를 반환 합니다.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소는 q u e 또는 빈는 q u e 다음에 나오는 위치를 주소 지정 하는 임의 액세스 반복기입니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 **시작** 에 할당 되는 `const_iterator`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **시작** 에 할당 되는 **반복기**, e q u e 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_begin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="a-namedequecbegina-dequecbegin"></a><a name="deque__cbegin"></a>  deque:: cbegin  
 범위의 첫 번째 요소를 주소 지정하는 `const` 반복기를 반환합니다.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>반환 값  
 범위의 첫 번째 요소 또는 빈 범위의 끝 바로 다음 위치를 가리키는 `const` 임의 액세스 반복기입니다(빈 범위의 경우 `cbegin() == cend()`).  
  
### <a name="remarks"></a>설명  
 `cbegin` 반환 값을 사용하여 범위의 요소를 수정할 수 없습니다.  
  
 `begin()` 멤버 함수 대신 이 멤버 함수를 사용하여 반환 값이 `const_iterator`임을 보장할 수 있습니다. 일반적으로 함께에서 사용 되는 [자동](../cpp/auto-cpp.md) 형식 추론 키워드, 다음 예제와 같이 합니다. 예제에서는 고려 `Container` 수정 가능 하 (비- `const`) 지 원하는 모든 종류의 컨테이너 `begin()` 및 `cbegin()`합니다.  
  
```cpp  
 
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namedequecenda-dequecend"></a><a name="deque__cend"></a>  deque:: cend  
 범위에서 마지막 요소 바로 다음의 위치를 주소 지정하는 `const` 반복기를 반환합니다.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>반환 값  
 범위 끝의 바로 다음을 가리키는 임의 액세스 반복기입니다.  
  
### <a name="remarks"></a>설명  
 `cend`는 반복기가 범위 끝을 통과했는지 여부를 테스트하는 데 사용됩니다.  
  
 `end()` 멤버 함수 대신 이 멤버 함수를 사용하여 반환 값이 `const_iterator`임을 보장할 수 있습니다. 일반적으로 함께에서 사용 되는 [자동](../cpp/auto-cpp.md) 형식 추론 키워드, 다음 예제와 같이 합니다. 예제에서는 고려 `Container` 수정 가능 하 (비- `const`) 지 원하는 모든 종류의 컨테이너 `end()` 및 `cend()`합니다.  
  
```cpp  
 
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 `cend`에서 반환한 값은 역참조되지 않아야 합니다.  
  
##  <a name="a-namedequecleara-dequeclear"></a><a name="deque__clear"></a>  deque:: clear  
 q u e의 모든 요소를 지웁니다.  
  
```  
void clear();
```  
  
### <a name="example"></a>예제  
  
```  
// deque_clear.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the deque is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the deque is initially 3  
The size of the deque after clearing is 0  
```  
  
##  <a name="a-namedequeconstiteratora-dequeconstiterator"></a><a name="deque__const_iterator"></a>  deque:: const_iterator  
 임의 액세스 반복기를 제공 하는 형식에서 액세스 하 고 읽을 수는 **const** 요소에는 q u e.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>설명  
 `const_iterator` 형식을 사용하여 요소의 값을 수정할 수는 없습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [다시](#deque__back)합니다.  
  
##  <a name="a-namedequeconstpointera-dequeconstpointer"></a><a name="deque__const_pointer"></a>  deque:: const_pointer  
 에 대 한 포인터를 제공 된 `const` 요소에는 q u e.  
  
```unstlib  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>설명  
 `const_pointer` 형식을 사용하여 요소의 값을 수정할 수는 없습니다.  [반복기](#deque__iterator) e q u e 요소에 액세스 하는 경우가 더 많습니다.  
  
##  <a name="a-namedequeconstreferencea-dequeconstreference"></a><a name="deque__const_reference"></a>  deque:: const_reference  
 에 대 한 참조를 제공 하는 형식은 **const** 읽고 수행 하기 위해 deque에 저장 된 요소 **const** 작업 합니다.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>설명  
 `const_reference` 형식을 사용하여 요소의 값을 수정할 수는 없습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_const_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const deque <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequeconstreverseiteratora-dequeconstreverseiterator"></a><a name="deque__const_reverse_iterator"></a>  deque:: const_reverse_iterator  
 읽을 수 있는 임의 액세스 반복기를 제공 하는 형식 **const** 요소에는 q u e.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식 `const_reverse_iterator` 요소 값을 수정할 수 없습니다 및 deque 반대 방향으로 반복 하는 데 사용 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [rbegin](#deque__rbegin) 선언 및 반복기를 사용 하는 방법의 예입니다.  
  
##  <a name="a-namedequecrbegina-dequecrbegin"></a><a name="deque__crbegin"></a>  deque:: crbegin  
 역방향된 deque의 첫 번째 요소에는 상수 반복기를 반환합니다.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>반환 값  
 const 역방향 임의 액세스 반복기 역순된 첫 번째 요소를 주소 지정 [e q u e](../standard-library/deque-class.md) 해제 된 마지막 요소의 주소를 지정 하거나 `deque`합니다.  
  
### <a name="remarks"></a>설명  
 반환 값이 `crbegin`이면 `deque` 개체를 수정할 수 없습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_crbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator v1_Iter;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of deque is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed deque is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of deque is 1.  
The first element of the reversed deque is 2.  
```  
  
##  <a name="a-namedequecrenda-dequecrend"></a><a name="deque__crend"></a>  deque:: crend  
 역방향된 deque에서 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 상수 반복기를 반환 합니다.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>반환 값  
 const 역방향 역순에서 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 임의 액세스 반복기 [e q u e](../standard-library/deque-class.md) (반전된 deque 첫 번째 요소 앞에 위치).  
  
### <a name="remarks"></a>설명  
 `crend` 사용 되는 역순으로 `deque` 것 처럼 [array::cend](../standard-library/array-class-stl.md#array__cend) 와 함께 사용 되는 `deque`합니다.  
  
 반환 값으로 `crend` (적절 하 게 감소)는 `deque` 개체를 수정할 수 없습니다.  
  
 `crend` 역방향 반복기의 q u e의 끝에 도달 했습니다 여부를 테스트에 사용할 수 있습니다.  
  
 `crend`에서 반환한 값은 역참조되지 않아야 합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_crend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namedequedequea-dequedeque"></a><a name="deque__deque"></a>  deque:: deque  
 특정 크기의 또는 특정 값의 또는 요소나 특정 할당 자가와 몇 가지 다른 e q u e의 일부 또는 복사본으로 deque를 생성합니다.  
  
```  
deque();

explicit deque(
    const Allocator& Al);

explicit deque(
    size_type Count);

deque(
    size_type Count,  
    const Type& Val);

deque(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

deque(
    const deque& Right);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);

deque(
    initializer_list<value_type>  
IList,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Al`|이 개체에 사용할 할당자 클래스입니다.|  
|`Count`|생성 된 deque에 있는 요소의 수입니다.|  
|`Val`|생성 된 deque에 있는 요소의 값입니다.|  
|`Right`|e q u e 생성된 deque를 복사본으로입니다.|  
|`First`|복사할 요소의 범위에서 첫 번째 요소의 위치입니다.|  
|`Last`|복사할 요소의 범위를 벗어난 첫 번째 요소의 위치입니다.|  
|`IList`|복사할 initializer_list입니다.|  
  
### <a name="remarks"></a>설명  
 모든 생성자는 할당자 개체를 저장 ( `Al`)는 q u e를 초기화 합니다.  
  
 처음 두 생성자는 빈 초기 e q u e;를 지정합니다. 두 번째 할당자 형식 지정 ( `_Al`) 사용할 수 있습니다.  
  
 세 번째 생성자는 지정된 된 수의 반복을 지정 ( ` count`) 클래스에 대 한 기본값의 요소 `Type`합니다.  
  
 네 번째와 다섯 번째 생성자는 반복 된 지정 ( `Count`) 값의 요소 ` val`합니다.  
  
 q u e의 복사본을 지정 하는 여섯 번째 생성자는 `Right`합니다.  
  
 일곱 번째 및 여덟 번째 생성자는 범위를 복사 `[First, Last)` 는 q u e입니다.  
  
 일곱 번째 생성자는 이동 하 여 q u e `Right`합니다.  
  
 여덟 번째 생성자는 initializer_list의 내용을 복사합니다.  
  
 중간 다시 할당을 수행하는 생성자는 없습니다.  
  
### <a name="example"></a>예제  
  
```  
/ compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <forward_list>  
  
int main()  
{  
    using namespace std;  
  
    forward_list<int> f1{ 1, 2, 3, 4 };  
  
    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });  
  
    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1(3);  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2(5, 2);  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4(c2);  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5(c4.begin(), c4_Iter);  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for (int i : c1)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for (int i : c2)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for (int i : c3)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for (int i : c4)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for (int i : c5)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for (int i : c6)  
        cout << i << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7(move(c6));  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =";  
    for (int i : c7)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    for (int i : c9)  
        cout << i << " ";  
    cout << endl;  
  
    int x = 3;  
}  
// deque_deque.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
    using namespace std;  
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1( 3 );  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2( 5, 2 );  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3( 3, 1, c2.get_allocator( ) );  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4( c2 );  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin( );  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5( c4.begin( ), c4_Iter );  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin( );  
   c4_Iter++;  
   c4_Iter++;  
   c4_Iter++;  
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
        initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
        cout << *c1_Iter << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
        cout << *c2_Iter << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
        cout << *c3_Iter << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )  
        cout << *c4_Iter << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )  
        cout << *c5_Iter << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )  
        cout << *c6_Iter << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7( move(c6) );  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =" ;  
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )  
        cout << " " << *c7_Iter;  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    or (int i : c9)  
        cout << i << " ";  
    cout << endl;  
}  
```  
  
##  <a name="a-namedequedifferencetypea-dequedifferencetype"></a><a name="deque__difference_type"></a>  deque:: difference_type  
 동일한 deque 내에서 요소를 참조 하는 두 반복기 사이의 차이 제공 하는 형식입니다.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>설명  
 `difference_type`은 두 포인터 사이의 요소로도 설명할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <deque>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   deque <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namedequeemplacea-dequeemplace"></a><a name="deque__emplace"></a>  deque:: emplace  
 Deque 지정 된 위치에 생성 된 요소를 삽입 합니다.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`_Where`|위치는 [e q u e](../standard-library/deque-class.md) 첫 번째 요소를 삽입 하는 위치입니다.|  
|` val`|`deque`에 삽입되는 요소의 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 함수는 q u e에 새 요소를 삽입 한 위치를 가리키는 반복기를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 모든 삽입 작업 비용이 많이 들 수 있습니다, 참조 `deque` 대 한 설명은 `deque` 성능입니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_emplace.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="a-namedequeemplacebacka-dequeemplaceback"></a><a name="deque__emplace_back"></a>  deque:: emplace_back  
 에 deque의 끝에 생성 된 요소를 추가 합니다.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|` val`|끝에 추가 되는 요소는 [e q u e](../standard-library/deque-class.md)합니다.|  
  
### <a name="example"></a>예제  
  
```  
// deque_emplace_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_back( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemplacefronta-dequeemplacefront"></a><a name="deque__emplace_front"></a>  deque:: emplace_front  
 에 deque의 끝에 생성 된 요소를 추가 합니다.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|` val`|시작 부분에 추가 되는 요소는 [e q u e](../standard-library/deque-class.md)합니다.|  
  
### <a name="example"></a>예제  
  
```  
// deque_emplace_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_front( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemptya-dequeempty"></a><a name="deque__empty"></a>  deque:: empty  
 deque 비어 있는지 테스트 합니다.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 는 deque 비어 있는 경우 **false** 는 deque 비어 있지 않은 경우.  
  
### <a name="example"></a>예제  
  
```  
// deque_empty.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The deque is empty." << endl;  
   else  
      cout << "The deque is not empty." << endl;  
}  
```  
  
```Output  
The deque is not empty.  
```  
  
##  <a name="a-namedequeenda-dequeend"></a><a name="deque__end"></a>  deque:: end  
 q u e에서 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 반복기를 반환 합니다.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>반환 값  
 q u e에서 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 임의 액세스 반복기입니다. deque 비어 있으면 deque:: end deque:: begin의 = =.  
  
### <a name="remarks"></a>설명  
 **최종** 반복기의 q u e의 끝에 도달 했는지 여부를 테스트 하는 데 사용 됩니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_end.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // deque <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The deque is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The deque is now: 10 400 30  
```  
  
##  <a name="a-namedequeerasea-dequeerase"></a><a name="deque__erase"></a>  deque:: erase  
 지정 된 위치에서 deque의 요소 또는 요소의 범위를 제거합니다.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Where`  
 q u e에서 제거할 요소의 위치입니다.  
  
 ` first`  
 첫 번째 요소의 위치는 q u e에서 제거 합니다.  
  
 ` last`  
 마지막 요소 바로 뒤의 위치는 q u e에서 제거 합니다.  
  
### <a name="return-value"></a>반환 값  
 제거 된 요소에 남아 있는 첫 번째 요소를 지정 하는 임의 액세스 반복기 또는 이러한 요소가 없으면 deque의 끝에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 대 한 자세한 내용은 **지우기**, 참조 [deque:: erase 및 deque:: clear](../misc/deque-erase-and-deque-clear.md)합니다.  
  
 **erase** 예외를 throw 할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_erase.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial deque is: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the deque becomes:  ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, deque becomes: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The initial deque is: 10 20 30 40 50   
After erasing the first element, the deque becomes:  20 30 40 50   
After erasing all elements but the first, deque becomes: 20   
```  
  
##  <a name="a-namedequefronta-dequefront"></a><a name="deque__front"></a>  deque:: front  
 에 deque 첫 번째 요소에 대 한 참조를 반환합니다.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>반환 값  
 deque 비어 있으면 반환 되는 정의 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 `front` 에 할당 되는 `const_reference`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `front` 에 할당 되는 **참조**, e q u e 개체를 수정할 수 있습니다.  
  
 _SECURE_SCL 1 컴파일하는 경우 요소는 빈 deque에 액세스 하려고 하면 런타임 오류가 발생 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// deque_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.front( );  
   const int& ii = c1.front( );  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The second integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 11  
```  
  
##  <a name="a-namedequegetallocatora-dequegetallocator"></a><a name="deque__get_allocator"></a>  deque:: get_allocator  
 q u e를 생성 하는 데 사용 되는 할당자 개체의 복사본을 반환 합니다.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>반환 값  
 q u e에서 사용 되는 할당자입니다.  
  
### <a name="remarks"></a>설명  
 Deque 클래스의 할당자는 클래스가 저장소를 관리 하는 방법을 지정 합니다. STL 컨테이너 클래스와 함께 제공되는 기본 할당자를 사용하면 대부분의 프로그래밍 요구 사항을 충족할 수 있습니다. 할당자 클래스를 직접 작성하고 사용하는 방법에 대해서는 고급 C++ 항목에서 다룹니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_get_allocator.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   deque <int> c1;  
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   deque <int> c3( c1.get_allocator( ) );  
  
   deque <int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namedequeinserta-dequeinsert"></a><a name="deque__insert"></a>  deque:: insert  
 Deque 지정 된 위치에 요소 또는 다양 한 요소 또는 요소의 범위를 삽입합니다.  
  
```  
iterator insert(
    const_iterator Where,  
    const Type& Val);

iterator insert(
    const_iterator Where,  
    Type&& Val);

void insert(
    iterator Where,  
    size_type Count,  
    const Type& Val);

template <class InputIterator>  
void insert(
    iterator Where,  
    InputIterator First,  
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Where`|첫 번째 요소를 삽입 하는 대상 deque의 위치입니다.|  
|`Val`|q u e에 삽입 되는 요소의 값입니다.|  
|`Count`|q u e에 삽입 되는 요소의 수입니다.|  
|`First`|인수 deque 복사할 요소 범위에서 첫 번째 요소의 위치입니다.|  
|`Last`|인수 deque 복사할 요소의 범위를 벗어나는 첫 번째 요소의 위치입니다.|  
|`IList`|삽입할 요소는 initializer_list입니다.|  
  
### <a name="return-value"></a>반환 값  
 처음 두 insert 함수는 q u e에 새 요소를 삽입 한 위치를 가리키는 반복기를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 모든 삽입 작업은 비용이 수 있습니다.  
  
##  <a name="a-namedequeiteratora-dequeiterator"></a><a name="deque__iterator"></a>  deque:: iterator  
 읽거나는 q u e의 모든 요소를 수정할 수 있는 임의 액세스 반복기를 제공 하는 형식입니다.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식 **반복기** 요소의 값을 수정 하는 것입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [시작](#deque__begin)합니다.  
  
##  <a name="a-namedequemaxsizea-dequemaxsize"></a><a name="deque__max_size"></a>  deque:: max_size  
 q u e의 최대 길이 반환합니다.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>반환 값  
 q u e의 최대 허용 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_max_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "The maximum possible length of the deque is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namedequeoperatorata-dequeoperator"></a><a name="deque__operator_at"></a>  deque:: operator]  
 지정된 된 위치에는 deque 요소에 대 한 참조를 반환합니다.  
  
```  
reference operator[](size_type _Pos);

const_reference operator[](size_type _Pos) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Pos`  
 위치는 e q u e 요소를 참조할 수입니다.  
  
### <a name="return-value"></a>반환 값  
 위치가 지정 되어 있는 인수에는 요소에 대 한 참조입니다. 지정 된 위치는 q u e의 크기 보다 크면 결과 정의 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 `operator[]` 에 할당 되는 `const_reference`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `operator[]` 에 할당 되는 **참조**, e q u e 개체를 수정할 수 있습니다.  
  
 를 _SECURE_SCL 1로 컴파일할 때에 deque의 범위 밖에 서 요소에 액세스 하려고 하면 런타임 오류가 발생 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// deque_op_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   cout << "The first integer of c1 is " << c1[0] << endl;  
   int& i = c1[1];  
   cout << "The second integer of c1 is " << i << endl;  
  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 20  
```  
  
##  <a name="a-namedequeoperatoreqa-dequeoperator"></a><a name="deque__operator_eq"></a>  deque:: operator =  
 다른 e q u e에서 요소를 사용 하 여이 deque의 요소를 대체 합니다.  
  
```  
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|` right`|새 콘텐츠를 제공 하는 deque 합니다.|  
  
### <a name="remarks"></a>설명  
 이 q u e에 요소를 복사 하는 첫 번째 재정의 ` right`, 할당의 소스입니다. 이 q u e에 요소를 이동 하는 두 번째 재정의 ` right`합니다.  
  
 연산자를 실행 하기 전에이 q u e에 포함 된 요소가 제거 됩니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_operator_as.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
using namespace std;  
  
typedef deque<int> MyDeque;  
  
template<typename MyDeque> struct S;  
  
template<typename MyDeque> struct S<MyDeque&> {  
  static void show( MyDeque& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
    cout << endl;  
  }  
};  
  
template<typename MyDeque> struct S<MyDeque&&> {  
  static void show( MyDeque&& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
cout << " via unnamed rvalue reference " << endl;  
  }  
};  
  
int main( )  
{  
   MyDeque d1, d2;  
  
   d1.push_back(10);  
   d1.push_back(20);  
   d1.push_back(30);  
   d1.push_back(40);  
   d1.push_back(50);  
  
   cout << "d1 = " ;  
   S<MyDeque&>::show( d1 );  
  
   d2 = d1;  
   cout << "d2 = ";  
   S<MyDeque&>::show( d2 );  
  
   cout << "     ";  
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );  
 }  
```  
  
##  <a name="a-namedequepointera-dequepointer"></a><a name="deque__pointer"></a>  deque:: pointer  
 요소에 대 한 포인터를 제공 된 [e q u e](../standard-library/deque-class.md)합니다.  
  
```unstlib  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>설명  
 형식 **포인터** 요소의 값을 수정 하는 것입니다.  [반복기](#deque__iterator) e q u e 요소에 액세스 하는 경우가 더 많습니다.  
  
##  <a name="a-namedequepopbacka-dequepopback"></a><a name="deque__pop_back"></a>  deque:: pop_back  
 q u e의 끝에 요소를 삭제합니다.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>설명  
 마지막 요소는 비워 둘 수 없습니다. `pop_back`은 예외를 throw할 수 없습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_pop_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the deque, the "  
      "last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the deque, the last element is: 1  
```  
  
##  <a name="a-namedequepopfronta-dequepopfront"></a><a name="deque__pop_front"></a>  deque:: pop_front  
 q u e의 시작 부분에 요소를 삭제 합니다.  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>설명  
 첫 번째 요소는 비워둘 수 없습니다. `pop_front`은 예외를 throw할 수 없습니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_pop_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the "  
      "deque, the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the deque, the first element is: 2  
```  
  
##  <a name="a-namedequepushbacka-dequepushback"></a><a name="deque__push_back"></a>  deque:: push_back  
 q u e의 끝에 요소를 추가 합니다.  
  
```  
void push_back(const Type& val);

void push_back(Type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|` val`|q u e의 끝에 추가 요소입니다.|  
  
### <a name="remarks"></a>설명  
 deque 낮으면 예외가 throw 되 면 변경 되지 않은 상태로 하 고 예외가 다시 throw 됩니다.  
  
##  <a name="a-namedequepushfronta-dequepushfront"></a><a name="deque__push_front"></a>  deque:: push_front  
 q u e의 시작 부분에 요소를 추가 합니다.  
  
```  
    void push_front(const Type& val);

void push_front(Type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|` val`|q u e의 시작 부분에 추가 된 요소입니다.|  
  
### <a name="remarks"></a>설명  
 deque 낮으면 예외가 throw 되 면 변경 되지 않은 상태로 하 고 예외가 다시 throw 됩니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_push_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a deque of strings  
   deque <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="a-namedequerbegina-dequerbegin"></a><a name="deque__rbegin"></a>  deque:: rbegin  
 역방향된 deque의 첫 번째 요소에 반복기를 반환합니다.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>반환 값  
 역방향 임의 액세스 반복기 역방향된 deque의 첫 번째 요소 주소를 지정 하거나 반전된 deque에서 마지막 요소의 주소를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 `rbegin` 역방향된 deque와 함께 사용 됩니다 것 처럼 [시작](#deque__begin) 는 q u e와 함께 사용 됩니다.  
  
 하는 경우의 반환 값 `rbegin` 에 할당 되는 `const_reverse_iterator`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `rbegin` 에 할당 되는 `reverse_iterator`, e q u e 개체를 수정할 수 있습니다.  
  
 `rbegin` 사용할 수 있습니다 역방향으로 반복할는 q u e.  
  
### <a name="example"></a>예제  
  
```  
// deque_rbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error   
   // would have resulted in the line modifying an element   
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rbegin( );  
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;  
  
   cout << "The deque contains the elements: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << "in that order.";  
   cout << endl;  
  
   // rbegin can be used to iterate through a deque in reverse order  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  // This would have caused an error if a   
                    // const_reverse iterator had been declared as   
                    // noted above  
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
Last element in the deque is 30.  
The deque contains the elements: 10 20 30 in that order.  
The reversed deque is: 30 20 10   
Last element in deque is now 40.  
```  
  
##  <a name="a-namedequereferencea-dequereference"></a><a name="deque__reference"></a>  deque:: reference  
 q u e에 저장 된 요소에 대 한 참조를 제공 하는 형식입니다.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>예제  
  
```  
// deque_reference.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequerenda-dequerend"></a><a name="deque__rend"></a>  deque:: rend  
 역방향된 deque에서 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 반복기를 반환 합니다.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>반환 값  
 역방향된 deque (반전된 deque 첫 번째 요소 앞에 위치)의 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 역방향 임의 액세스 반복기입니다.  
  
### <a name="remarks"></a>설명  
 `rend` 역방향된 deque와 함께 사용 됩니다 것 처럼 [끝](#deque__end) 는 q u e와 함께 사용 됩니다.  
  
 하는 경우의 반환 값 `rend` 에 할당 되는 `const_reverse_iterator`, e q u e 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `rend` 에 할당 되는 `reverse_iterator`, e q u e 개체를 수정할 수 있습니다.  
  
 `rend` 사용할 수는 역방향 반복기의 q u e의 끝에 있는지 여부를 테스트 합니다.  
  
 `rend`에서 반환한 값은 역참조되지 않아야 합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_rend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
   // If the following line had replaced the line above, an error  
   // would have resulted in the line modifying an element  
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --; // Decrementing a reverse iterator moves it forward   
                // in the deque (to point to the first element here)  
   cout << "The first element in the deque is: " << *c1_rIter << endl;  
  
   cout << "The deque is: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of   
   // the elements of a reversed deque  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--; // Decrementing the reverse iterator moves it backward   
               // in the reversed deque (to the last element here)  
 *c1_rIter = 40; // This modification of the last element would   
                   // have caused an error if a const_reverse   
                   // iterator had been declared (as noted above)  
   cout << "The modified reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The first element in the deque is: 10  
The deque is: 10 20 30   
The reversed deque is: 30 20 10   
The modified reversed deque is: 30 20 40   
```  
  
##  <a name="a-namedequeresizea-dequeresize"></a><a name="deque__resize"></a>  deque:: resize  
 새 크기는 q u e를 지정합니다.  
  
```  
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Newsize`  
 q u e의 새 크기입니다.  
  
 ` val`  
 새 크기가 큰 경우에 q u e에 추가할 새 요소의 값을 원래 크기입니다. 값을 생략 하면 새 요소 클래스에 대 한 기본 값이 할당 됩니다.  
  
### <a name="remarks"></a>설명  
 Deque의 크기를 사용 하면 요청된 된 크기 보다 작으면 `_Newsize`, 요청된 된 크기에 도달할 때까지 요소는 q u e에 추가 됩니다.  
  
 deque 크기에 도달할 때까지 q u e의 끝과 가장 가까운 요소가 삭제 됩니다 deque의 크기가 요청된 된 크기 보다 클 경우 `_Newsize`합니다.  
  
 q u e의 현재 크기와 요청된 된 크기가 동일한 경우 없는 작업도 있습니다.  
  
 [크기](#deque__size) 는 q u e의 현재 크기를 반영 합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_resize.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{   
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is: 4  
The value of the last element is 40  
The size of c1 is now: 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namedequereverseiteratora-dequereverseiterator"></a><a name="deque__reverse_iterator"></a>  deque:: reverse_iterator  
 읽거나 역방향된 deque의 요소를 수정할 수 있는 임의 액세스 반복기를 제공 하는 형식입니다.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식 `reverse_iterator` 는 q u e에서 반복 하는 데 사용 합니다.  
  
### <a name="example"></a>예제  
  Rbegin에 대 한 예제를 참조 하십시오.  
  
##  <a name="a-namedequeshrinktofita-dequeshrinktofit"></a><a name="deque__shrink_to_fit"></a>  deque:: shrink_to_fit  
 여분의 용량을 삭제합니다.  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>설명  
 여부를 확인 하려면 휴대용 없으므로 `shrink_to_fit` 사용 하는 저장소를 줄일 수는 [e q u e](../standard-library/deque-class.md)합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   //deque <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
}  
```  
  
```Output  
Current size of v1 = 1  
Current size of v1 = 1  
```  
  
##  <a name="a-namedequesizea-dequesize"></a><a name="deque__size"></a>  deque:: size  
 에 deque 요소 수를 반환합니다.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 q u e의 현재 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   c1.push_back( 1 );  
   i = c1.size( );  
   cout << "The deque length is " << i << "." << endl;  
  
   c1.push_back( 2 );  
   i = c1.size( );  
   cout << "The deque length is now " << i << "." << endl;  
}  
```  
  
```Output  
The deque length is 1.  
The deque length is now 2.  
```  
  
##  <a name="a-namedequesizetypea-dequesizetype"></a><a name="deque__size_type"></a>  deque:: size_type  
 q u e에 있는 요소의 수를 계산 하는 형식입니다.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>예제  
  예를 참조 [크기](#deque__size)합니다.  
  
##  <a name="a-namedequeswapa-dequeswap"></a><a name="deque__swap"></a>  deque:: swap  
 두 deque의 요소를 교환합니다.  
  
```  
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>  
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 대체 되는 요소를 제공 하는 deque 또는 q u e와 교환할 요소입니다 deque ` left`합니다.  
  
 ` left`  
 q u e와 교환할 요소입니다 deque ` right`합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_swap.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2, c3;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap<>(c1, c2);  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original deque c1 is: 1 2 3  
After swapping with c2, deque c1 is: 10 20  
After swapping with c3, deque c1 is: 100  
After swapping with c2, deque c1 is: 1 2 3  
```  
  
##  <a name="a-namedequevaluetypea-dequevaluetype"></a><a name="deque__value_type"></a>  deque:: value_type  
 q u e에 저장 된 데이터 형식을 나타내는 형식입니다.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>설명  
 `value_type` 템플릿 매개 변수는 동의어 **형식**합니다.  
  
### <a name="example"></a>예제  
  
```  
// deque_value_type.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   deque<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

