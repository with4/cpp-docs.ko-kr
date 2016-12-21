---
title: "벡터 클래스 1 | Microsoft Docs"
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
  - "std::vector"
  - "vector"
  - "std.vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector 클래스"
ms.assetid: a3e0a8f8-7565-4fe0-93e4-e4d74ae1b70d
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 벡터 클래스 1
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL 벡터 클래스는 선형 정렬에서 지정된 형식의 요소를 정렬하고 모든 요소에 대한 빠른 임의 액세스를 허용하는 시퀀스 컨테이너의 템플릿 클래스입니다. 임의 액세스 성능이 가장 중요할 때 시퀀스에 대한 기본 컨테이너로 사용해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Type, class Allocator = allocator<Type>>  
class vector  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Type*  
 벡터에 저장되는 요소 데이터 형식입니다.  
  
 `Allocator`  
 벡터의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항이 며 기본값은 **할당자***\< 형식>합니다.*  
  
## <a name="remarks"></a>설명  
 벡터를 사용하면 시퀀스 끝에서 상수 시간 삽입 및 삭제할 수 있습니다. 벡터 중간에 요소를 삽입하거나 삭제하려면 선형 시간이 필요합니다. 성능에는 [deque 클래스](../standard-library/deque-class.md) 컨테이너는 시퀀스의 시작과 끝에서 삽입과 삭제 우수 합니다.  [list 클래스](../standard-library/list-class.md) 컨테이너는 시퀀스 내 모든 위치에서 삽입과 삭제 우수 합니다.  
  
 멤버 함수가 벡터 개체에 포함되는 시퀀스를 현재 저장소 용량보다 더 크게 늘려야 할 때 벡터 다시 할당이 수행됩니다. 다른 삽입 및 지우기에서 시퀀스 내의 여러 저장소 주소가 변경될 수 있습니다. 이러한 모든 경우 시퀀스의 변경되는 부분을 가리키는 반복기 또는 참조가 올바르지 않은 상태가 됩니다. 재할당이 수행되지 않으면 삽입/삭제 지점 앞의 반복기와 참조만 올바른 상태로 유지됩니다.  
  
  [벡터 \< bool> 클래스](../standard-library/vector-bool-class.md) bool 형식의 요소에 대 한 템플릿 클래스 벡터의 전체 특수화로, 특수화에 사용 되는 기본 유형에 대 한 할당자를 포함 합니다.  
  
  [벡터 \< bool> 클래스를 참조](../standard-library/vector-bool-class.md#vector_lt_bool_gt___reference_class) 는 해당 개체가 벡터 내의 요소 (단일 비트)에 대 한 참조를 제공할 수 있는 중첩된 클래스 \< bool> 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[벡터](#vector__vector)|특정 크기의 벡터 또는 특정 값의 요소나 특정 `allocator`가 포함된 벡터를 생성하거나 다른 벡터의 복사본으로 벡터를 생성합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[allocator_type](#vector__allocator_type)|벡터 개체의 `allocator` 클래스를 나타내는 형식입니다.|  
|[const_iterator](#vector__const_iterator)|벡터에 있는 `const` 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[const_pointer](#vector__const_pointer)|벡터의 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[const_reference](#vector__const_reference)|`const` 작업을 읽고 수행하기 위해 벡터에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|[const_reverse_iterator](#vector__const_reverse_iterator)|벡터의 모든 `const` 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[difference_type](#vector__difference_type)|벡터 내 두 요소 주소 간의 차이를 제공하는 형식입니다.|  
|[반복기](#vector__iterator)|벡터에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[포인터](#vector__pointer)|벡터에서 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](#vector__reference)|벡터에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|[reverse_iterator](#vector__reverse_iterator)|역방향 벡터에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[size_type](#vector__size_type)|벡터의 요소 수를 계산하는 형식입니다.|  
|[value_type](#vector__value_type)|벡터에 저장된 데이터 형식을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[할당](#vector__assign)|벡터를 지우고 지정된 요소를 빈 벡터에 복사합니다.|  
|[에서](#vector__at)|벡터의 지정된 위치에 있는 요소에 대한 참조를 반환합니다.|  
|[뒤로](#vector__back)|벡터의 마지막 요소에 대한 참조를 반환합니다.|  
|[시작](#vector__begin)|벡터의 첫 번째 요소에 대한 임의 액세스 반복기를 반환합니다.|  
|[용량](#vector__capacity)|저장소를 더 할당하지 않고 벡터가 포함할 수 있는 요소의 수를 반환합니다.|  
|[cbegin](#vector__cbegin)|벡터의 첫 번째 요소에 대한 임의 액세스 const 반복기를 반환합니다.|  
|[cend](#vector__cend)|벡터 끝의 바로 다음을 가리키는 임의 액세스 const 반복기를 반환합니다.|  
|[crbegin](#vector__crbegin)|역방향 벡터의 첫 번째 요소에 대해 const 반복기를 반환합니다.|  
|[crend](#vector__crend)|역방향 벡터 끝에 대해 const 반복기를 반환합니다.|  
|[지우기](#vector__clear)|벡터의 요소를 지웁니다.|  
|[데이터](#vector__data)|벡터의 첫 번째 요소에 대한 포인터를 반환합니다.|  
|[emplace](#vector__emplace)|내부에서 생성된 요소를 벡터의 지정된 위치에 삽입합니다.|  
|[emplace_back](#vector__emplace_back)|내부에서 생성된 요소를 벡터의 끝에 추가합니다.|  
|[빈](#vector__empty)|벡터 컨테이너가 비어 있는지 테스트합니다.|  
|[끝](#vector__end)|벡터 끝을 가리키는 임의 액세스 반복기를 반환합니다.|  
|[지우기](#vector__erase)|벡터의 지정된 위치에서 요소 또는 요소 범위를 제거합니다.|  
|[앞면](#vector__front)|벡터의 첫 번째 요소에 대한 참조를 반환합니다.|  
|[get_allocator](#vector__get_allocator)|벡터에서 사용하는 `allocator` 클래스에 개체를 반환합니다.|  
|[삽입](#vector__insert)|요소 또는 요소의 수를 벡터의 지정된 위치에 삽입합니다.|  
|[max_size](#vector__max_size)|벡터의 최대 길이를 반환합니다.|  
|[pop_back](#vector__pop_back)|벡터의 끝에 있는 요소를 삭제합니다.|  
|[push_back](#vector__push_back)|벡터 끝에 요소를 추가합니다.|  
|[rbegin](#vector__rbegin)|역방향 벡터의 첫 번째 요소에 대한 반복기를 반환합니다.|  
|[rend](#vector__rend)|역방향 벡터 끝에 대해 반복기를 반환합니다.|  
|[예약](#vector__reserve)|벡터 개체에 대한 저장소의 최소 길이를 예약합니다.|  
|[크기 조정](#vector__resize)|벡터의 새 크기를 지정합니다.|  
|[shrink_to_fit](#vector__shrink_to_fit)|여분의 용량을 삭제합니다.|  
|[크기](#vector__size)|벡터에 있는 요소 수를 반환합니다.|  
|[스왑](#vector__swap)|두 벡터의 요소를 교환합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 &#91; &#93;](#vector__operator_at)|지정된 위치에서 벡터 요소에 참조를 반환합니다.|  
|[연산자 =](#vector__operator_eq)|벡터의 요소를 다른 벡터의 복사본으로 바꿉니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 벡터>  
  
 **네임스페이스:** std  
  
##  <a name="a-namevectorallocatortypea-vectorallocatortype"></a><a name="vector__allocator_type"></a>  vector:: allocator_type  
 벡터 개체의 할당자 클래스를 나타내는 형식입니다.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>설명  
 `allocator_type` 템플릿 매개 변수는 동의어 **할당자입니다.**  
  
### <a name="example"></a>예제  
  예를 참조 [get_allocator](#vector__get_allocator) 사용 하는 예제에 대 한 `allocator_type`합니다.  
  
##  <a name="a-namevectorassigna-vectorassign"></a><a name="vector__assign"></a>  vector:: assign  
 벡터를 지우고 지정된 요소를 빈 벡터에 복사합니다.  
  
```  
void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);
```  
  
### <a name="parameters"></a>매개 변수  
 `First`  
 복사할 요소의 범위에서 첫 번째 요소의 위치입니다.  
  
 `Last`  
 복사할 요소의 범위를 벗어난 첫 번째 요소의 위치입니다.  
  
 `Count`  
 벡터에 삽입되는 요소의 복사본 수입니다.  
  
 `Val`  
 벡터에 삽입되는 요소의 값입니다.  
  
 `IList`  
 삽입할 요소를 포함하는 initializer_list입니다.  
  
### <a name="remarks"></a>설명  
 벡터에서 기존 요소를 지운 후 원래 벡터의 지정한 요소 범위를 벡터에 삽입하거나 지정한 값의 새 요소 복사본을 벡터에 삽입합니다.  
  
### <a name="example"></a>예제  
  
```  
/ vector_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> v1, v2, v3;  
  
    v1.push_back(10);  
    v1.push_back(20);  
    v1.push_back(30);  
    v1.push_back(40);  
    v1.push_back(50);  
  
    cout << "v1 = ";  
    for (auto& v : v1){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v2.assign(v1.begin(), v1.end());  
    cout << "v2 = ";  
    for (auto& v : v2){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign(7, 4);  
    cout << "v3 = ";  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign({ 5, 6, 7 });  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namevectorata-vectorat"></a><a name="vector__at"></a>  vector:: at  
 벡터의 지정된 위치에 있는 요소에 대한 참조를 반환합니다.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Pos`  
 벡터에서 참조할 요소의 아래 첨자 또는 위치 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 인수에서 아래 첨자로 설정된 요소에 대한 참조입니다. 경우 `_Off` 벡터의 크기 보다 크면 **에서** 예외를 throw 합니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 **에서** 에 할당 되는 `const_reference`, 벡터 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **에서** 에 할당 되는 **참조**, 벡터 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_at.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const int &i = v1.at( 0 );  
   int &j = v1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namevectorbacka-vectorback"></a><a name="vector__back"></a>  vector:: back  
 벡터의 마지막 요소에 대한 참조를 반환합니다.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터의 마지막 요소입니다. 벡터가 비어 있으면 반환 값이 정의되지 않습니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 **다시** 에 할당 되는 `const_reference`, 벡터 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **다시** 에 할당 되는 **참조**, 벡터 개체를 수정할 수 있습니다.  
  
 _SECURE_SCL 1로 컴파일할 때 빈 벡터의 요소에 액세스하려고 하면 런타임 오류가 발생합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// vector_back.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.back( );  
   const int& ii = v1.front( );  
  
   cout << "The last integer of v1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of v1 is "<< ii << endl;  
}  
```  
  
##  <a name="a-namevectorbegina-vectorbegin"></a><a name="vector__begin"></a>  vector:: begin  
 벡터의 첫 번째 요소에 대한 임의 액세스 반복기를 반환합니다.  
  
```  
const_iterator begin() const;

 
iterator begin();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소를 주소 지정 하는 임의 액세스 반복기는 `vector` 또는 빈 다음에 나오는 위치를 `vector`합니다. 항상 함께 반환 된 값을 비교 해야 [vector:: end](#vector__end) 유효한 지 확인 합니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 `begin` 에 할당 되는 [vector:: const_iterator](#vector__const_iterator),  `vector` 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `begin` 에 할당 되는 [vector:: iterator](#vector__iterator),  `vector` 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_begin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::iterator c1_Iter;  
    vector<int>::const_iterator c1_cIter;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_Iter = c1.begin();  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1_Iter = c1.begin();  
 *c1_Iter = 20;  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    // The following line would be an error because iterator is const  
    // *c1_cIter = 200;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="a-namevectorcapacitya-vectorcapacity"></a><a name="vector__capacity"></a>  vector:: capacity  
 저장소를 더 할당하지 않고 벡터가 포함할 수 있는 요소의 수를 반환합니다.  
  
```  
size_type capacity() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터에 할당된 저장소의 현재 길이입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수 [크기를 조정](#vector__resize) 에 맞게 충분 한 메모리를 할당 한 경우 효율성이 높아집니다. 멤버 함수를 사용 하 여 [예약](#vector__reserve) 할당 된 메모리 양을 지정 합니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_capacity.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 1 );  
   cout << "The length of storage allocated is "  
        << v1.capacity( ) << "." << endl;  
  
   v1.push_back( 2 );  
   cout << "The length of storage allocated is now "  
        << v1.capacity( ) << "." << endl;  
}  
```  
  
```Output  
The length of storage allocated is 1.  
The length of storage allocated is now 2.  
```  
  
##  <a name="a-namevectorcbegina-vectorcbegin"></a><a name="vector__cbegin"></a>  vector:: cbegin  
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
  
##  <a name="a-namevectorcenda-vectorcend"></a><a name="vector__cend"></a>  vector:: cend  
 범위에서 마지막 요소 바로 다음의 위치를 주소 지정하는 `const` 반복기를 반환합니다.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>반환 값  
 범위 끝의 바로 다음을 가리키는 `const` 임의 액세스 반복기입니다.  
  
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
  
##  <a name="a-namevectorcleara-vectorclear"></a><a name="vector__clear"></a>  vector:: clear  
 벡터의 요소를 지웁니다.  
  
```  
void clear();
```  
  
### <a name="example"></a>예제  
  
```  
// vector_clear.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "The size of v1 is " << v1.size( ) << endl;  
   v1.clear( );  
   cout << "The size of v1 after clearing is " << v1.size( ) << endl;  
}  
```  
  
```Output  
The size of v1 is 3  
The size of v1 after clearing is 0  
```  
  
##  <a name="a-namevectorconstiteratora-vectorconstiterator"></a><a name="vector__const_iterator"></a>  vector:: const_iterator  
 읽을 수 있는 임의 액세스 반복기를 제공 하는 형식은 **const** 벡터의 요소입니다.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>설명  
 `const_iterator` 형식을 사용하여 요소의 값을 수정할 수는 없습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [다시](#vector__back) 사용 하는 예제에 대 한 `const_iterator`합니다.  
  
##  <a name="a-namevectorconstpointera-vectorconstpointer"></a><a name="vector__const_pointer"></a>  vector:: const_pointer  
 에 대 한 포인터를 제공 하는 형식은 **const** 벡터의 요소입니다.  
  
```  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>설명  
 `const_pointer` 형식을 사용하여 요소의 값을 수정할 수는 없습니다.  
  
  [반복기](#vector__iterator) 벡터 요소에 액세스 하는 경우가 더 많습니다.  
  
##  <a name="a-namevectorconstreferencea-vectorconstreference"></a><a name="vector__const_reference"></a>  vector:: const_reference  
 에 대 한 참조를 제공 하는 형식은 **const** 읽고 수행 하기 위해 벡터에 저장 된 요소 **const** 작업 합니다.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>설명  
 `const_reference` 형식을 사용하여 요소의 값을 수정할 수는 없습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_const_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const vector <int> v2 = v1;  
   const int &i = v2.front( );  
   const int &j = v2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as v2 is const  
   // v2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namevectorconstreverseiteratora-vectorconstreverseiterator"></a><a name="vector__const_reverse_iterator"></a>  vector:: const_reverse_iterator  
 읽을 수 있는 임의 액세스 반복기를 제공 하는 형식 **const** 벡터의 요소입니다.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식 `const_reverse_iterator` 를 수정할 수 없으며 요소 값 벡터를 역방향으로 반복 하는 데 사용 됩니다.  
  
### <a name="example"></a>예제  
  참조 [rbegin](#vector__rbegin) 선언 및 반복기를 사용 하는 방법의 예입니다.  
  
##  <a name="a-namevectorcrbegina-vectorcrbegin"></a><a name="vector__crbegin"></a>  vector:: crbegin  
 역방향 벡터의 첫 번째 요소에 대해 const 반복기를 반환합니다.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>반환 값  
 const 역방향 임의 액세스 반복기 역순된 첫 번째 요소를 주소 지정 [벡터](../standard-library/vector-class.md) 해제 된 마지막 요소의 주소를 지정 하거나 `vector`합니다.  
  
### <a name="remarks"></a>설명  
 반환 값이 `crbegin`이면 `vector` 개체를 수정할 수 없습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_crbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="a-namevectorcrenda-vectorcrend"></a><a name="vector__crend"></a>  vector:: crend  
 역방향된 벡터의 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 상수 반복기를 반환 합니다.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>반환 값  
 const 역방향 역순에서 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 임의 액세스 반복기 [벡터](../standard-library/vector-class.md) (위치 해제 된 첫 번째 요소 앞에 `vector`).  
  
### <a name="remarks"></a>설명  
 `crend` 사용 되는 역순으로 `vector` 것 처럼 [vector:: cend](#vector__cend) 와 함께 사용 되는 `vector`합니다.  
  
 반환 값으로 `crend` (적절 하 게 감소)는 `vector` 개체를 수정할 수 없습니다.  
  
 `crend`를 사용하여 역방향 반복기가 `vector` 끝에 도달했는지 여부를 테스트할 수 있습니다.  
  
 `crend`에서 반환한 값은 역참조되지 않아야 합니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_crend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
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
  
##  <a name="a-namevectordataa-vectordata"></a><a name="vector__data"></a>  vector:: data  
 벡터의 첫 번째 요소에 대한 포인터를 반환합니다.  
  
```  
const_pointer data() const;

 
pointer data();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소에 대 한 포인터는 [벡터](../standard-library/vector-class.md) 또는 빈 다음에 나오는 위치를 `vector`합니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_data.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::pointer c1 ptr;  
    vector<int>::const_pointer c1_cPtr;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_cPtr = c1.data();  
    for (size_t n = c1.size(); 0 < n; --n, c1_cPtr++)  
    {  
        cout << " " << *c1_cPtr;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1 ptr = c1.data();  
 *c1 ptr = 20;  
    for (size_t n = c1.size(); 0 < n; --n, c1 ptr++)  
    {  
        cout << " " << *c1 ptr;  
    }  
    cout << endl;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="a-namevectordifferencetypea-vectordifferencetype"></a><a name="vector__difference_type"></a>  vector:: difference_type  
 동일한 벡터 내의 요소를 참조하는 두 반복기 간의 차이를 제공하는 형식입니다.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>설명  
 A `difference_type` 해당 주소를 포함 하는 요소에 대 한 포인터 때문에 두 포인터 사이의 요소로 수로 설명도 있습니다.  
  
  [반복기](#vector__iterator) 벡터 요소에 액세스 하는 경우가 더 많습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <vector>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   vector <int> c1;  
   vector <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   vector <int>::difference_type   df_typ1, df_typ2, df_typ3;  
  
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
  
##  <a name="a-namevectoremplacea-vectoremplace"></a><a name="vector__emplace"></a>  vector:: emplace  
 내부에서 생성된 요소를 벡터의 지정된 위치에 삽입합니다.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`_Where`|위치는 [벡터](../standard-library/vector-class.md) 첫 번째 요소를 삽입 하는 위치입니다.|  
|` val`|`vector`에 삽입되는 요소의 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 함수는 새 요소를 `vector`에 삽입한 위치를 가리키는 반복기를 반환합니다.  
  
### <a name="remarks"></a>설명  
 모든 삽입 작업 비용이 많이 들 수 있습니다, 참조 [vector 클래스](../standard-library/vector-class.md) 대 한 설명은 `vector` 성능입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_emplace.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
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
  
##  <a name="a-namevectoremplacebacka-vectoremplaceback"></a><a name="vector__emplace_back"></a>  vector:: emplace_back  
 내부에서 생성된 요소를 벡터의 끝에 추가합니다.  
  
```  
template <class... Types>  
void emplace_back(Types&&... _Args);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Args`|생성자 인수입니다. 이 함수는 제공되는 인수에 따라 호출할 생성자 오버로드를 유추합니다.|  
  
### <a name="example"></a>예제  
  
```cpp  
  
#include <vector>  
struct obj  
{  
   obj(int, double) {}  
};  
  
int main()  
{  
   std::vector<obj> v;  
   v.emplace_back(1, 3.14); // obj in created in place in the vector  
}  
  
```  
  
##  <a name="a-namevectoremptya-vectorempty"></a><a name="vector__empty"></a>  vector:: empty  
 벡터가 비어 있는지 테스트 합니다.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 벡터가 비어 있으면 **false** 벡터 비어 있지 않은 경우.  
  
### <a name="example"></a>예제  
  
```  
// vector_empty.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
  
   if ( v1.empty( ) )  
      cout << "The vector is empty." << endl;  
   else  
      cout << "The vector is not empty." << endl;  
}  
```  
  
```Output  
The vector is not empty.  
```  
  
##  <a name="a-namevectorenda-vectorend"></a><a name="vector__end"></a>  vector:: end  
 마지막 바로 다음 반복기를 반환합니다.  
  
```  
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터의 마지막 바로 다음 반복기입니다. 벡터가 비어 있으면 `vector::end() == vector::begin()`입니다.  
  
### <a name="remarks"></a>설명  
 하는 경우의 반환 값 **끝** 형식의 변수에 할당 `const_iterator`, 벡터 개체를 수정할 수 없습니다. 하는 경우의 반환 값 **끝** 형식의 변수에 할당 **반복기**, 벡터 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_end.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )  
      cout << *v1_Iter << endl;  
}  
```  
  
```Output  
1  
2  
```  
  
##  <a name="a-namevectorerasea-vectorerase"></a><a name="vector__erase"></a>  vector:: erase  
 벡터의 지정된 위치에서 요소 또는 요소 범위를 제거합니다.  
  
```  
iterator erase(
    const_iterator _Where);

iterator erase(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`_Where`|벡터에서 제거할 요소의 위치입니다.|  
|` first`|벡터에서 제거되는 첫 번째 요소의 위치입니다.|  
|` last`|벡터에서 제거되는 마지막 요소 바로 뒤의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 제거되는 요소 뒤에 남아 있는 첫 번째 요소를 지정하는 반복기이거나, 남아 있는 요소가 없는 경우에는 벡터 끝에 대한 포인터입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_erase.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
   v1.push_back( 40 );  
   v1.push_back( 50 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) + 1, v1.begin( ) + 3 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
v1 = 10 20 30 40 50  
v1 = 20 30 40 50  
v1 = 20 50  
```  
  
##  <a name="a-namevectorfronta-vectorfront"></a><a name="vector__front"></a>  vector:: front  
 벡터의 첫 번째 요소에 대한 참조를 반환합니다.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터 개체의 첫 번째 요소에 대한 참조입니다. 벡터가 비어 있으면 반환이 정의되지 않습니다.  
  
### <a name="remarks"></a>설명  
 `front`의 반환 값이 `const_reference`로 할당되는 경우, 벡터 개체는 수정할 수 없습니다. 하는 경우의 반환 값 `front` 에 할당 되는 **참조**, 벡터 개체를 수정할 수 있습니다.  
  
 _SECURE_SCL 1로 컴파일할 때 빈 벡터의 요소에 액세스하려고 하면 런타임 오류가 발생합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```  
// vector_front.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.front( );  
   const int& ii = v1.front( );  
  
   cout << "The first integer of v1 is "<< i << endl;  
   // by incrementing i, we move the the front reference to the second element  
   i++;  
   cout << "Now, the first integer of v1 is "<< i << endl;  
}  
```  
  
##  <a name="a-namevectorgetallocatora-vectorgetallocator"></a><a name="vector__get_allocator"></a>  vector:: get_allocator  
 벡터를 생성 하는 데 사용 되는 할당자 개체의 복사본을 반환 합니다.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터에서 사용되는 할당자입니다.  
  
### <a name="remarks"></a>설명  
 Vector 클래스의 할당자는 클래스가 저장소를 관리 하는 방법을 지정 합니다. STL 컨테이너 클래스와 함께 제공되는 기본 할당자를 사용하면 대부분의 프로그래밍 요구 사항을 충족할 수 있습니다. 할당자 클래스를 직접 작성하고 사용하는 방법에 대해서는 고급 C++ 항목에서 다룹니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_get_allocator.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   vector<int> v1;  
   vector<int, allocator<int> > v2 = vector<int, allocator<int> >(allocator<int>( )) ;  
  
   // v3 will use the same allocator class as v1  
   vector <int> v3( v1.get_allocator( ) );  
  
   vector<int>::allocator_type xvec = v3.get_allocator( );  
   // You can now call functions on the allocator class used by vec  
}  
```  
  
##  <a name="a-namevectorinserta-vectorinsert"></a><a name="vector__insert"></a>  vector:: insert  
 하나 또는 여러 개의 요소나 요소의 범위를 벡터의 지정된 위치에 삽입합니다.  
  
```  
iterator insert(
    const_iterator _Where,  
    const Type& val);

iterator insert(
    const_iterator _Where,  
    Type&& val);

void insert(
    const_iterator _Where,  
    size_type count,  
    const Type& val);

template <class InputIterator>  
void insert(
    const_iterator _Where,  
    InputIterator first,  
    InputIterator last);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`_Where`|벡터에서 첫 번째 요소를 삽입하는 위치입니다.|  
|` val`|벡터에 삽입되는 요소의 값입니다.|  
|` count`|벡터에 삽입되는 요소의 수입니다.|  
|` first`|복사할 요소의 범위에서 첫 번째 요소의 위치입니다.|  
|` last`|복사할 요소의 범위를 벗어나는 첫 번째 요소의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 처음 두 `insert` 함수는 새 요소가 벡터에 삽입된 위치를 가리키는 반복기를 반환합니다.  
  
### <a name="remarks"></a>설명  
 모든 삽입 작업 비용이 많이 들 수 있습니다, 참조 [vector 클래스](../standard-library/vector-class.md) 대 한 설명은 `vector` 성능입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_insert.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( ) + 1, 40 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   v1.insert( v1.begin( ) + 2, 4, 50 );  
  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( )+1, v1.begin( )+2, v1.begin( )+4 );  
   cout << "v1 =";  
   for (Iter = v1.begin( ); Iter != v1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
   vv1.insert( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      vector < vector <int> >::iterator Iter;  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
v1 = 10 40 20 30  
v1 = 10 40 50 50 50 50 20 30  
v1 = 10 50 50 40 50 50 50 50 20 30  
vv1[0] = 10 50 50 40 50 50 50 50 20 30  
```  
  
##  <a name="a-namevectoriteratora-vectoriterator"></a><a name="vector__iterator"></a>  vector:: iterator  
 벡터에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식 **반복기** 요소의 값을 수정 하는 것입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [시작](#vector__begin)합니다.  
  
##  <a name="a-namevectormaxsizea-vectormaxsize"></a><a name="vector__max_size"></a>  vector:: max_size  
 벡터의 최대 길이를 반환합니다.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터의 최대 허용 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_max_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   i = v1.max_size( );     
   cout << "The maximum possible length of the vector is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namevectoroperatorata-vectoroperator"></a><a name="vector__operator_at"></a>  vector:: operator]  
 지정된 위치에서 벡터 요소에 참조를 반환합니다.  
  
```  
reference operator[](size_type Pos);

const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Pos`|벡터 요소의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 지정된 위치가 컨테이너의 크기보다 크거나 같을 경우 결과가 정의되지 않습니다.  
  
### <a name="remarks"></a>설명  
 `operator[]`의 반환 값이 `const_reference`로 할당되는 경우, 벡터 개체는 수정할 수 없습니다. `operator[]`의 반환 값이 참조로 할당되는 경우는 벡터 개체를 수정할 수 있습니다.  
  
 _SECURE_SCL 1로 컴파일할 때 (사용 하 여 제어 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)), 벡터 경계 밖에 서 요소에 액세스 하려고 하면 런타임 오류가 발생 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_op_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   int& i = v1[1];  
   cout << "The second integer of v1 is " << i << endl;  
}  
```  
  
##  <a name="a-namevectoroperatoreqa-vectoroperator"></a><a name="vector__operator_eq"></a>  vector:: operator =  
 벡터의 요소를 다른 벡터의 복사본으로 바꿉니다.  
  
```  
vector& operator=(const vector& right);

vector& operator=(vector&& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|` right`| [벡터](../standard-library/vector-class.md) 에 복사 되는 `vector`합니다.|  
  
### <a name="remarks"></a>설명  
 `vector`는 `operator=`에서 기존 요소를 지운 후에 ` right`의 내용을 `vector`로 복사하거나 이동합니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_operator_as.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v1, v2, v3;  
   vector<int>::iterator iter;  
  
   v1.push_back(10);  
   v1.push_back(20);  
   v1.push_back(30);  
   v1.push_back(40);  
   v1.push_back(50);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namevectorpointera-vectorpointer"></a><a name="vector__pointer"></a>  vector:: pointer  
 벡터에서 요소에 대한 포인터를 제공하는 형식입니다.  
  
```  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>설명  
 형식 **포인터** 요소의 값을 수정 하는 것입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_pointer.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v;  
   v.push_back( 11 );  
   v.push_back( 22 );  
  
   vector<int>::pointer ptr = &v[0];  
   cout << *ptr << endl;  
   ptr++;  
   cout << *ptr << endl;  
 *ptr = 44;  
   cout << *ptr << endl;  
}  
```  
  
```Output  
11  
22  
44  
```  
  
##  <a name="a-namevectorpopbacka-vectorpopback"></a><a name="vector__pop_back"></a>  vector:: pop_back  
 벡터의 끝에 있는 요소를 삭제합니다.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>설명  
 코드 예제를 참조 하십시오. [vector:: push_back ()](#vector__push_back)합니다.  
  
##  <a name="a-namevectorpushbacka-vectorpushback"></a><a name="vector__push_back"></a>  vector:: push_back  
 벡터 끝에 요소를 추가합니다.  
  
```  
void push_back(const T& Val);

 
void push_back(T&& Val);
```  
  
### <a name="parameters"></a>매개 변수  
 `Val`  
 벡터의 끝에 추가된 요소에 할당할 값입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
template <typename T> void print_elem(const T& t) {  
    cout << "(" << t << ") ";  
}  
  
template <typename T> void print_collection(const T& t) {  
    cout << "  " << t.size() << " elements: ";  
  
    for (const auto& p : t) {  
        print_elem(p);  
    }  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(10 + i);  
    }  
  
    cout << "vector data: " << endl;  
    print_collection(v);  
  
    // pop_back() until it's empty, printing the last element as we go  
    while (v.begin() != v.end()) {   
        cout << "v.back(): "; print_elem(v.back()); cout << endl;  
        v.pop_back();  
    }  
}  
```  
  
##  <a name="a-namevectorrbegina-vectorrbegin"></a><a name="vector__rbegin"></a>  vector:: rbegin  
 역방향 벡터의 첫 번째 요소에 대한 반복기를 반환합니다.  
  
```  
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>반환 값  
 역방향 임의 액세스 반복기 역방향된 벡터의 첫 번째 요소 주소를 지정 하거나 반전된 벡터에 있는 마지막 요소의 주소를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 `rbegin`의 반환 값이 `const_reverse_iterator`로 할당되는 경우, 벡터 개체는 수정할 수 없습니다. 하는 경우의 반환 값 `rbegin` 에 할당 되는 `reverse_iterator`, 벡터 개체를 수정할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_rbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.rbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="a-namevectorreferencea-vectorreference"></a><a name="vector__reference"></a>  vector:: reference  
 벡터에 저장된 요소에 대한 참조를 제공하는 형식입니다.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>예제  
  참조 [에서](#vector__at) 사용 하는 방법의 예 **참조** 벡터 클래스에서.  
  
##  <a name="a-namevectorrenda-vectorrend"></a><a name="vector__rend"></a>  vector:: rend  
 역방향된 벡터의 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 반복기를 반환 합니다.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>반환 값  
 역방향된 벡터 (반전된 된 벡터의 첫 번째 요소 앞의 위치)의 마지막 요소 다음에 나오는 위치의 주소를 지정 하는 역방향 임의 액세스 반복기입니다.  
  
### <a name="remarks"></a>설명  
 `rend` 역방향된 벡터와 함께 사용 됩니다 것 처럼 [끝](#vector__end) 벡터와 함께 사용 됩니다.  
  
 하는 경우의 반환 값 `rend` 에 할당 되는 `const_reverse_iterator`, 벡터 개체를 수정할 수 없습니다. 하는 경우의 반환 값 `rend` 에 할당 되는 `reverse_iterator`, 벡터 개체를 수정할 수 있습니다.  
  
 `rend` 역방향 반복기가 벡터의 끝을 도달 했는지 여부를 테스트에 사용할 수 있습니다.  
  
 `rend`에서 반환한 값은 역참조되지 않아야 합니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_rend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::reverse_iterator v1_rIter;  
  
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
  
##  <a name="a-namevectorreservea-vectorreserve"></a><a name="vector__reserve"></a>  vector:: reserve  
 벡터 개체의 최소 저장소 길이를 예약하며 필요한 경우 공간을 할당합니다.  
  
```  
void reserve(size_type count);
```  
  
### <a name="parameters"></a>매개 변수  
 ` count`  
 벡터에 대해 할당할 최소 저장소 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_reserve.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
```  
  
##  <a name="a-namevectorresizea-vectorresize"></a><a name="vector__resize"></a>  vector:: resize  
 벡터의 새 크기를 지정합니다.  
  
```  
void resize(size_type Newsize);

void resize(size_type Newsize, Type Val);
```  
  
### <a name="parameters"></a>매개 변수  
 `Newsize`  
 벡터의 새 크기입니다.  
  
 `Val`  
 새 크기가 원래 크기보다 큰 경우 벡터에 추가된 새 요소의 초기화 값입니다. 이 값이 생략되면 새 개체는 기본 생성자를 사용합니다.  
  
### <a name="remarks"></a>설명  
 컨테이너의 크기가 요청된 크기 `Newsize`보다 작으면 요청한 크기에 도달할 때까지 벡터에 요소가 추가됩니다. 컨테이너의 크기가 요청된 크기보다 크면 컨테이너가 요청된 크기 `Newsize`에 도달할 때까지 컨테이너 끝에서 가장 가까운 요소가 삭제됩니다. 컨테이너의 현재 크기와 요청된 크기가 동일하면 아무런 작업도 실행되지 않습니다.  
  
 [크기](#vector__size) 벡터의 현재 크기를 반영 합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vectorsizing.cpp  
// compile with: /EHsc /W4  
// Illustrates vector::reserve, vector::max_size,  
// vector::resize, vector::resize, and vector::capacity.  
//  
// Functions:  
//  
//    vector::max_size - Returns maximum number of elements vector could  
//                       hold.  
//  
//    vector::capacity - Returns number of elements for which memory has  
//                       been allocated.  
//  
//    vector::size - Returns number of elements in the vector.  
//  
//    vector::resize - Reallocates memory for vector, preserves its  
//                     contents if new size is larger than existing size.  
//  
//    vector::reserve - Allocates elements for vector to ensure a minimum  
//                      size, preserving its contents if the new size is  
//                      larger than existing size.  
//  
//    vector::push_back - Appends (inserts) an element to the end of a  
//                        vector, allocating memory for it if necessary.  
//  
//////////////////////////////////////////////////////////////////////  
  
// The debugger cannot handle symbols more than 255 characters long.  
// STL often creates symbols longer than that.  
// The warning can be disabled:  
//#pragma warning(disable:4786)  
  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
    cout << endl;  
}  
  
void printvstats(const vector<int>& v) {  
    cout << "   the vector's size is: " << v.size() << endl;  
    cout << "   the vector's capacity is: " << v.capacity() << endl;  
    cout << "   the vector's maximum size is: " << v.max_size() << endl;  
}  
  
int main()  
{  
    // declare a vector that begins with 0 elements.  
    vector<int> v;  
  
    // Show statistics about vector.  
    cout << endl << "After declaring an empty vector:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Add one element to the end of the vector.  
    v.push_back(-1);  
    cout << endl << "After adding an element:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
    cout << endl << "After adding 10 elements:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(6);  
    cout << endl << "After resizing to 6 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(9, 999);  
    cout << endl << "After resizing to 9 elements with an initialization value of 999:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(12);  
    cout << endl << "After resizing to 12 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Ensure there's room for at least 1000 elements.  
    v.reserve(1000);  
    cout << endl << "After vector::reserve(1000):" << endl;  
    printvstats(v);  
  
    // Ensure there's room for at least 2000 elements.  
    v.resize(2000);  
    cout << endl << "After vector::resize(2000):" << endl;  
    printvstats(v);  
}  
```  
  
##  <a name="a-namevectorreverseiteratora-vectorreverseiterator"></a><a name="vector__reverse_iterator"></a>  vector:: reverse_iterator  
 역방향 벡터에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 `reverse_iterator` 형식은 벡터를 역방향으로 반복하는 데 사용됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [rbegin](#vector__rbegin)합니다.  
  
##  <a name="a-namevectorshrinktofita-vectorshrinktofit"></a><a name="vector__shrink_to_fit"></a>  vector:: shrink_to_fit  
 여분의 용량을 삭제합니다.  
  
```  
void shrink_to_fit();
```  
  
### <a name="example"></a>예제  
  
```  
// vector_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
Current capacity of v1 = 1  
```  
  
##  <a name="a-namevectorsizea-vectorsize"></a><a name="vector__size"></a>  vector:: size  
 벡터에 있는 요소 수를 반환합니다.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 벡터의 현재 길이입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   v1.push_back( 1 );  
   i = v1.size( );  
   cout << "Vector length is " << i << "." << endl;  
  
   v1.push_back( 2 );  
   i = v1.size( );  
   cout << "Vector length is now " << i << "." << endl;  
}  
```  
  
```Output  
Vector length is 1.  
Vector length is now 2.  
```  
  
##  <a name="a-namevectorsizetypea-vectorsizetype"></a><a name="vector__size_type"></a>  vector:: size_type  
 벡터의 요소 수를 계산하는 형식입니다.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>예제  
  예를 참조 [용량](#vector__capacity)합니다.  
  
##  <a name="a-namevectorswapa-vectorswap"></a><a name="vector__swap"></a>  vector:: swap  
 두 벡터의 요소를 교환합니다.  
  
```  
void swap(
    vector<Type, Allocator>& right);

friend void swap(
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` right`  
 교환할 요소를 제공하는 벡터이거나, ` left` 벡터와 요소를 교환할 벡터입니다.  
  
 ` left`  
 ` right` 벡터와 요소를 교환할 벡터입니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_swap.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1, v2;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 3 );  
  
   v2.push_back( 10 );  
   v2.push_back( 20 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
   cout << endl;  
  
   v1.swap( v2 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
}  
```  
  
```Output  
The number of elements in v1 = 3  
The number of elements in v2 = 2  
  
The number of elements in v1 = 2  
The number of elements in v2 = 3  
```  
  
##  <a name="a-namevectorvaluetypea-vectorvaluetype"></a><a name="vector__value_type"></a>  vector:: value_type  
 벡터에 저장된 데이터 형식을 나타내는 형식입니다.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>설명  
 `value_type` 템플릿 매개 변수는 동의어 **형식**합니다.  
  
### <a name="example"></a>예제  
  
```  
// vector_value_type.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
##  <a name="a-namevectorvectora-vectorvector"></a><a name="vector__vector"></a>  vector:: vector  
 특정 크기의 벡터 또는 특정 값의 요소나 특정 할당자가 포함된 벡터를 생성하거나 다른 벡터의 일부분 또는 전체에 대한 복사본으로 벡터를 생성합니다.  
  
```  
vector();

explicit vector(
    const Allocator& Al);

explicit vector(
    size_type Count);

vector(
    size_type Count,  
    const Type& Val);

vector(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

vector(
    const vector& Right);

vector(
    vector&& Right);

vector(
    initializer_list<Type> IList,  
    const _Allocator& Al);

template <class InputIterator>  
vector(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
vector(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Al`|이 개체에 사용할 할당자 클래스입니다. [get_allocator](#vector__get_allocator) 개체에 대 한 할당자 클래스를 반환 합니다.|  
|`Count`|생성된 벡터에 있는 요소의 수입니다.|  
|`Val`|생성된 벡터에 있는 요소의 값입니다.|  
|`Right`|해당 복사본으로 벡터를 생성할 벡터입니다.|  
|`First`|복사할 요소의 범위에서 첫 번째 요소의 위치입니다.|  
|`Last`|복사할 요소의 범위를 벗어난 첫 번째 요소의 위치입니다.|  
|`IList`|복사할 elmeents를 포함 하는 initializer_list입니다.|  
  
### <a name="remarks"></a>설명  
 모든 생성자는 할당자 개체를 저장 ( `Al`) 및 벡터를 초기화 합니다.  
  
 처음 두 생성자는 빈 초기 벡터를 지정합니다. 두 번째에 할당자 형식을 명시적으로 지정 ( `Al`) 사용할 수 있습니다.  
  
 세 번째 생성자는 지정된 된 수의 반복을 지정 ( `Count`) 클래스에 대 한 기본값의 요소 `Type`합니다.  
  
 네 번째와 다섯 번째 생성자는 반복 된 지정 ( `Count`) 값의 요소 `Val`합니다.  
  
 여섯 번째 생성자는 `Right` 벡터의 복사본을 지정합니다.  
  
 일곱 번째 생성자는 `Right` 벡터를 이동합니다.  
  
 여덟 번째 생성자는 initializer_list를 사용하여 요소를 지정합니다.  
  
 아홉 번째 및 열 번째 생성자는 범위를 복사 [ `First`, `Last`) 벡터입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_ctor.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector <int>::iterator v1_Iter, v2_Iter, v3_Iter, v4_Iter, v5_Iter, v6_Iter;  
  
    // Create an empty vector v0  
    vector <int> v0;  
  
    // Create a vector v1 with 3 elements of default value 0  
    vector <int> v1(3);  
  
    // Create a vector v2 with 5 elements of value 2  
    vector <int> v2(5, 2);  
  
    // Create a vector v3 with 3 elements of value 1 and with the allocator   
    // of vector v2  
    vector <int> v3(3, 1, v2.get_allocator());  
  
    // Create a copy, vector v4, of vector v2  
    vector <int> v4(v2);  
  
    // Create a new temporary vector for demonstrating copying ranges  
    vector <int> v5(5);  
    for (auto i : v5) {  
        v5[i] = i;  
    }  
  
    // Create a vector v6 by copying the range v5[ first,  last)  
    vector <int> v6(v5.begin() + 1, v5.begin() + 3);  
  
    cout << "v1 =";  
    for (auto& v : v1){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v2 =";  
    for (auto& v : v2){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v3 =";  
    for (auto& v : v3){  
        cout << " " << v;  
    }  
    cout << endl;  
    cout << "v4 =";  
    for (auto& v : v4){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v5 =";  
    for (auto& v : v5){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v6 =";  
    for (auto& v : v6){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    // Move vector v2 to vector v7  
    vector <int> v7(move(v2));  
    vector <int>::iterator v7_Iter;  
  
    cout << "v7 =";  
    for (auto& v : v7){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    vector<int> v8{ { 1, 2, 3, 4 } };  
    for (auto& v : v8){  
        cout << " " << v ;  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
v1 = 0 0 0v2 = 2 2 2 2 2v3 = 1 1 1v4 = 2 2 2 2 2v5 = 0 1 2 3 4v6 = 1 2v7 = 2 2 2 2 21 2 3 4  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

