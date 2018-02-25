---
title: "&lt;memory&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::default_delete
- memory/std::dynamic_pointer_cast
- memory/std::get_deleter
- memory/std::get_pointer_safety
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- xmemory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
- memory/std::get_temporary_buffer
- memory/std::return_temporary_buffer
dev_langs:
- C++
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::swap [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: 070b6c9e532f1148484a3b7381c7ae13015b0a67
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltmemorygt-functions"></a>&lt;memory&gt; 함수
||||  
|-|-|-|  
|[addressof](#addressof)|[align](#align)|[allocate_shared](#allocate_shared)|  
|[const_pointer_cast](#const_pointer_cast)|[declare_no_pointers](#declare_no_pointers)|[declare_reachable](#declare_reachable)|  
|[default_delete](#default_delete)|[dynamic_pointer_cast](#dynamic_pointer_cast)|[get_deleter](#get_deleter)|  
|[get_pointer_safety](#get_pointer_safety)|[get_temporary_buffer](#get_temporary_buffer)|[make_shared](#make_shared)|  
|[make_unique](#make_unique)|[owner_less](#owner_less)|[return_temporary_buffer](#return_temporary_buffer)|  
|[static_pointer_cast](#static_pointer_cast)|[swap(C++ 표준 라이브러리)](#swap)|[undeclare_no_pointers](#undeclare_no_pointers)|  
|[undeclare_reachable](#undeclare_reachable)|[uninitialized_copy](#uninitialized_copy)|[uninitialized_copy_n](#uninitialized_copy_n)|  
|[uninitialized_fill](#uninitialized_fill)|[uninitialized_fill_n](#uninitialized_fill_n)|  
  
##  <a name="addressof"></a>  addressof  
 개체의 실제 주소를 가져옵니다.  
  
```  
template <class T>  
T* addressof(T& Val);
```  
  
### <a name="parameters"></a>매개 변수  
 `Val`  
 실제 주소를 가져올 개체 또는 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 오버로드된 `Val`가 있는 경우에도, `operator&()`에서 참조하는 개체 또는 함수의 실제 주소입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="align"></a>  align  
 지정된 크기의 저장소(지정된 정렬 사양을 기준으로 정렬됨)를 지정된 저장소의 첫 번째 가능한 주소에 정렬합니다.  
  
```  
void* align(
    size_t Alignment, // input  
    size_t Size,      // input  
    void*& Ptr,        // input/output  
    size_t& Space     // input/output
);
```  
  
### <a name="parameters"></a>매개 변수  

 `Alignment`  
 시도에 맞게 정렬됩니다.  
  
 `Size`  
 정렬된 저장소의 크기(바이트 단위)입니다.  
  
 `Ptr`  
 사용 가능한 인접 저장소 풀 중 사용할 저장소 풀의 시작 주소입니다. 이 매개 변수는 출력 매개 변수 이기도 고 맞춤에 성공 하면 새 시작 주소를 포함 하도록 설정 됩니다. `align()`이 성공하지 않을 경우 이 매개 변수는 수정되지 않습니다.  
  
 `Space`  
 정렬된 저장소를 만드는 데 사용하기 위해 `align()`에서 사용할 수 있는 총 공간입니다. 이 매개 변수는 출력 매개 변수이기도 하며, 정렬된 저장소 및 관련된 모든 연결된 오버헤드를 차감한 후 저장소 버퍼에 남아 있는 조정된 공간을 포함합니다.  
  
 `align()`이 성공하지 않을 경우 이 매개 변수는 수정되지 않습니다.  
  
### <a name="return-value"></a>반환 값  

 요청된 정렬된 버퍼가 사용 가능 공간에 맞지 않는 경우 null 포인터이며, 그렇지 않을 경우 `Ptr`의 새 값입니다.  
  
### <a name="remarks"></a>설명  

 수정된 `Ptr` 및 `Space` 매개 변수를 사용하면 `align()` 및 `Alignment`에 대해 다른 값을 사용하여 동일한 버퍼에서 `Size`을 반복적으로 호출할 수 있습니다. 다음 코드 조각은 `align()`을 사용하는 방법을 보여 줍니다.  
  
```cpp  
#include <type_traits> // std::alignment_of()  
#include <memory>  
//...  
char buffer[256]; // for simplicity  
size_t alignment = std::alignment_of<int>::value;  
void * ptr = buffer;  
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer  
  
while (std::align(alignment, sizeof(MyObj), ptr, space)) {  
    // You now have storage the size of MyObj, starting at ptr, aligned on   
    // int boundary. Use it here if you like, or save off the starting address  
    // contained in ptr for later use.  
    // ...  
    // Last, move starting pointer and decrease available space before  
    // the while loop restarts.  
    ptr = reinterpret_cast<char*>(ptr) + sizeof(MyObj);  
    space -= sizeof(MyObj);  
}  
// At this point, align() has returned a null pointer, signaling it is not  
// possible to allow more aligned storage in this buffer.   
```  
  
##  <a name="allocate_shared"></a>  allocate_shared  
 지정된 할당자를 사용하여 지정된 형식에 대해 할당되고 생성되는 개체에 대한 `shared_ptr`을 만듭니다. `shared_ptr`를 반환합니다.  
  
```  
template <class Type, class Allocator, class... Types>  
shared_ptr<Type>  
allocate_shared(Allocator Alloc, Types&&... Args);
```  
  
### <a name="parameters"></a>매개 변수  
 `Alloc`  
 개체를 만드는 데 사용된 할당자입니다.  
  
 `Args`  
 개체가 되는 0개 이상의 인수입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 `Alloc`에 의해 할당되고 생성된 대로 `Type(Args...)`에 대한 포인터인 `shared_ptr<Type>` 개체를 만듭니다.  
  
##  <a name="const_pointer_cast"></a>  const_pointer_cast  
 shared_ptr로 const_cast를 수행합니다.  
  
```  
template <class Ty, class Other>  
shared_ptr<Ty>  
const_pointer_cast(const shared_ptr<Other>& sp);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 반환된 공유 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 인수 공유 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 인수 공유 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `const_cast<Ty*>(sp.get())`가 null 포인터를 반환하는 경우 템플릿 함수는 빈 shared_ptr 개체를 반환합니다. 그러지 않은 경우 `sp`가 소유하는 리소스를 소유하는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md)`<Ty>` 개체를 반환합니다. `const_cast<Ty*>(sp.get())` 식이 유효해야 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__memory__const_pointer_cast.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
{   
    std::shared_ptr<int> sp0(new int);   
    std::shared_ptr<const int> sp1 =   
        std::const_pointer_cast<const int>(sp0);   
  
 *sp0 = 3;   
    std::cout << "sp1 == " << *sp1 << std::endl;   
  
    return (0);   
}
```  
  
```Output  
sp1 == 3  
```  
  
##  <a name="declare_no_pointers"></a>  declare_no_pointers  
 기본 주소 포인터와 블록 크기로 정의된 메모리 블록에 있는 문자에 추적 가능한 포인터가 포함될 수 없음을 가비지 수집기에 알립니다.  
  
```  
void declare_no_pointers(
    char* ptr,   
    size_t _Size);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|추적 가능한 포인터를 더 이상 포함하지 않는 첫 번째 문자의 주소입니다.|  
|`_Size`|추적 가능한 포인터를 포함하지 않는, `ptr`에서 시작하는 블록의 크기입니다.|  
  
### <a name="remarks"></a>설명  
 함수는 모든 가비지 수집기에 알립니다 하는 주소 범위 `[ ptr, ptr + _Size)` 추적이 가능한 포인터를 포함 하지 않도록 합니다. (할당 된 저장소에 대 한 모든 포인터 하지를 역참조 해야 액세스할 수 있도록 처리 하지 않는 한 합니다.)  
  
##  <a name="declare_reachable"></a>  declare_reachable  
 지정된 주소가 할당된 저장소 대한 것이며 접근할 수 있음을 가비지 컬렉션에 알립니다.  
  
```  
void declare_reachable(void* ptr);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptr`  
 연결할 수 있는 할당된 유효한 저장소 영역에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `ptr`이 null이 아니면 함수는 이제부터 `ptr`에 연결할 수 있고 할당된 유효한 저장소를 가리킴을 가비지 수집기에 알립니다.  
  
##  <a name="default_delete"></a>  default_delete  

`operator new`를 사용하여 할당된 개체를 삭제합니다. `unique_ptr`에 사용하는 데 적합합니다.  

```  
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>  
   default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;     
};  
```
### <a name="parameters"></a>매개 변수  
 `Ptr`  
 삭제할 개체에 대한 포인터입니다.  
  
 기타  
 삭제할 배열의 요소 형식입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 클래스는 `operator new`를 사용하여 할당된 스칼라 개체를 삭제하는 `deleter`를 설명하며 템플릿 클래스 `unique_ptr`와 함께 사용하기에 적합합니다. 이 템플릿 클래스에는 명시적 특수화 `default_delete<Type[]>`도 있습니다.  
  
##  <a name="dynamic_pointer_cast"></a>  dynamic_pointer_cast  
 shared_ptr로 동적 캐스팅합니다.  
  
```  
template <class Ty, class Other>  
shared_ptr<Ty>  
dynamic_pointer_cast(const shared_ptr<Other>& sp);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 반환된 공유 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 인수 공유 포인터에 의해 제어되는 형식입니다.  
  
 `sp`  
 인수 공유 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `dynamic_cast<Ty*>(sp.get())`가 null 포인터를 반환하는 경우 템플릿 함수는 빈 shared_ptr 개체를 반환합니다. 그러지 않은 경우 `sp`가 소유하는 리소스를 소유하는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md)`<Ty>` 개체를 반환합니다. `dynamic_cast<Ty*>(sp.get())` 식이 유효해야 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__memory__dynamic_pointer_cast.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
struct base   
{   
    virtual ~base() {}   
    int val;   
};   
  
struct derived   
    : public base   
{   
};   
  
int main()   
{   
    std::shared_ptr<base> sp0(new derived);   
    std::shared_ptr<derived> sp1 =   
        std::dynamic_pointer_cast<derived>(sp0);   
  
    sp0->val = 3;   
    std::cout << "sp1->val == " << sp1->val << std::endl;   
  
    return (0);   
}
```  
  
```Output  
sp1->val == 3  
```  
  
##  <a name="get_deleter"></a>  get_deleter
 shared_ptr에서 삭제자를 가져옵니다.  
  
```  
template <class D, class Ty>  
D* get_deleter(const shared_ptr<Ty>& sp);
```  
  
### <a name="parameters"></a>매개 변수  
 `D`  
 삭제자의 형식입니다.  
  
 `Ty`  
 공유 포인터에 의해 제어되는 형식입니다.  
  
 `sp`  
 공유 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md) 개체 `sp`에 속하는 `D` 형식의 삭제자에 대한 포인터를 반환합니다. `sp`에 삭제자가 없는 경우 또는 삭제자가 `D` 형식이 아닌 경우 함수는 0을 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__memory__get_deleter.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
struct base   
{   
    int val;   
};   
  
struct deleter   
{   
    void operator()(base *p)   
    {   
        delete p;   
    }   
};   
  
int main()   
{   
    std::shared_ptr<base> sp0(new base);   
  
    sp0->val = 3;   
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha   
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;   
  
    std::shared_ptr<base> sp1(new base, deleter());   
  
    sp0->val = 3;   
    std::cout << "get_deleter(sp1) != 0 == " << std::boolalpha   
        << (std::get_deleter<deleter>(sp1) != 0) << std::endl;   
  
    return (0);   
}  

```  
  
```Output  
get_deleter(sp0) != 0 == false  
get_deleter(sp1) != 0 == true  
```  
  
##  <a name="get_pointer_safety"></a>  get_pointer_safety  
 모든 가비지 수집기에서 간주된 포인터 안전 형식을 반환합니다.  
  
```  
pointer_safety get_pointer_safety();
```  
  
### <a name="remarks"></a>설명  
 함수에는 모든 자동 가비지 수집기에서 간주 된 포인터 안전 형식을 반환 합니다.  
  
##  <a name="get_temporary_buffer"></a>  get_temporary_buffer  
 지정된 수의 요소를 초과하지 않는 요소의 시퀀스를 위한 임시 저장소를 할당합니다.  
  
```  
template <class Type>  
pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```  
  
### <a name="parameters"></a>매개 변수  
 `count`  
 메모리를 할당하도록 요청한 최대 요소 수입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 구성 요소는 할당된 메모리에 대한 포인터이고, 두 번째 구성 요소는 저장할 수 있는 요소의 최대 수를 나타내는 버퍼의 크기를 제공하는 `pair`입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 메모리에 대한 요청을 만들며 성공하지 못할 수 있습니다. 버퍼가 할당되지 않은 경우 함수는 두 번째 구성 요소는 0이고 첫 번째 구성 요소는 null 포인터인 쌍을 반환합니다.  
  
 이 함수는 일시적인 메모리에만 사용해야 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// memory_get_temp_buf.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   // Create an array of ints  
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };  
   int count = sizeof ( intArray ) / sizeof ( int );  
   cout << "The number of integers in the array is: "   
      << count << "." << endl;  
  
   pair<int *, ptrdiff_t> resultPair;  
   resultPair = get_temporary_buffer<int>( count );  
  
   cout << "The number of elements that the allocated memory\n"  
        << "could store is given by: resultPair.second = "   
        << resultPair.second << "." << endl;  
}  
```  
  
```Output  
The number of integers in the array is: 9.  
The number of elements that the allocated memory  
could store is given by: resultPair.second = 9.  
```  
  
##  <a name="make_shared"></a>  make_shared  
 기본 할당자를 사용하여 하나 이상의 인수에서 작성된 할당된 개체를 가리키는 `shared_ptr`를 만들고 반환합니다. 지정된 형식의 개체와 `shared_ptr`을 모두 할당 및 생성하여 개체의 공유 소유권을 관리하고 `shared_ptr`을 반환합니다.  
  
```  
template <class Type, class... Types>  
shared_ptr<Type>  
make_shared(Types&&... _Args);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Args`|0개 이상의 생성자 인수입니다. 이 함수는 제공되는 인수에 따라 호출할 생성자 오버로드를 유추합니다.|  
  
### <a name="remarks"></a>설명  
 `make_shared`를 개체 및 `shared_ptr`을 만드는 간단하고 보다 효율적인 방법으로 사용하여 개체에 대한 공유 액세스를 동시에 관리할 수 있습니다. 의미상으로 다음 두 문은 동일합니다.  
  
```cpp  
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```  
  
 그러나 첫 번째 문은 두 개의 할당을 만들고, `shared_ptr` 개체의 할당이 성공한 후에 `Example`의 할당이 실패하면 명명되지 않은 `Example` 개체가 유출됩니다. `make_shared`를 사용하는 문은 관련된 함수 호출이 하나뿐이므로 더 간단합니다. 라이브러리가 개체와 스마트 포인터에 대해 단일 할당을 만들 수 있으므로 더 효율적입니다. 또한 더 빠르면서 메모리 조각화를 덜 유발하며, 둘 중 하나의 할당에서만 예외가 발생할 가능성이 없습니다. 개체를 참조하고 스마트 포인터의 참조 카운트를 업데이트하는 코드에 대한 집약성이 더 높아지므로 성능이 향상됩니다.  
  
 개체에 대한 공유 액세스가 필요하지 않은 경우에는 [make_unique](../standard-library/memory-functions.md#make_unique) 사용을 고려하세요. 개체에 대한 사용자 지정 할당자를 지정해야 하는 경우에는 [allocate_shared](../standard-library/memory-functions.md#allocate_shared)를 사하세요. deleter를 인수로 전달할 수 있는 방법이 없으므로 개체에 사용자 지정 deleter가 필요한 경우 `make_shared`를 사용할 수 없습니다.  
  
 다음 예에서는 특정 생성자 오버로드를 호출하여 형식에 대한 공유 포인터를 만드는 방법을 보여 줍니다.  
  
### <a name="example"></a>예  
  
```cpp  
// stl_make_shared.cpp  
// Compile by using: cl /W4 /EHsc stl_make_shared.cpp  
#include <iostream>  
#include <string>  
#include <memory>  
#include <vector>  
  
class Song {  
public:  
   std::wstring title_;  
   std::wstring artist_;  
  
   Song(std::wstring title, std::wstring artist) : title_(title), artist_(artist) {}  
   Song(std::wstring title) : title_(title), artist_(L"Unknown") {}  
};  
  
void CreateSharedPointers() {  
   // Okay, but less efficient to have separate allocations for  
   // Song object and shared_ptr control block.    
   auto song = new Song(L"Ode to Joy", L"Beethoven");  
   std::shared_ptr<Song> sp0(song);  
  
   // Use make_shared function when possible. Memory for control block  
   // and Song object are allocated in the same call:    
   auto sp1 = std::make_shared<Song>(L"Yesterday", L"The Beatles");  
   auto sp2 = std::make_shared<Song>(L"Blackbird", L"The Beatles");  
  
   // make_shared infers which constructor to use based on the arguments.  
   auto sp3 = std::make_shared<Song>(L"Greensleeves");  
  
   // The playlist vector makes copies of the shared_ptr pointers.  
   std::vector<std::shared_ptr<Song>> playlist;  
   playlist.push_back(sp0);  
   playlist.push_back(sp1);  
   playlist.push_back(sp2);  
   playlist.push_back(sp3);  
   playlist.push_back(sp1);  
   playlist.push_back(sp2);  
   for (auto&& sp : playlist) {  
      std::wcout << L"Playing " << sp->title_ <<   
         L" by " << sp->artist_ << L", use count: " <<   
         sp.use_count() << std::endl;  
   }  
}  
  
int main() {  
   CreateSharedPointers();  
}  
```  
  
  이 예에서는 다음과 같은 출력을 생성합니다.  
  
```Output  
Playing Ode to Joy by Beethoven, use count: 2  
Playing Yesterday by The Beatles, use count: 3  
Playing Blackbird by The Beatles, use count: 3  
Playing Greensleeves by Unknown, use count: 2  
Playing Yesterday by The Beatles, use count: 3  
Playing Blackbird by The Beatles, use count: 3  
```  
  
##  <a name="make_unique"></a>  make_unique  
 지정된 인수를 사용하여 생성되는, 지정된 형식의 개체에 대한 [unique_ptr](../standard-library/unique-ptr-class.md)을 만들고 반환합니다.  
  
```  
// make_unique<T> 
template <class T, class... Types>  
unique_ptr<T> 
make_unique(Types&&... Args)  
{  
    return (unique_ptr<T>(new T(forward<Types>(Args)...)));
}
  
// make_unique<T[]>  
template <class T>  
make_unique(size_t Size)   
{   
    return (unique_ptr<T>(new Elem[Size]()));
}  
 
// make_unique<T[N]> disallowed  
template <class T, class... Types>  
typename enable_if<extent<T>::value != 0, void>::type 
make_unique(Types&&...) = delete;  
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 `unique_ptr`이 가리키는 개체의 형식입니다.  
  
 `Types`  
 `Args`로 지정된 생성자 인수의 형식입니다.  
  
 `Args`  
 `T` 형식의 개체 생성자에 전달할 인수입니다.  
  
 `Elem`  
 `T` 형식 요소의 배열입니다.  
  
 `Size`  
 새 배열에 공간을 할당할 수 있는 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 오버로드는 단일 개체에 사용되고, 두 번째 오버로드는 배열에 대해 호출되고, 세 번째 오버로드는 형식 인수(make_unique\<T[N]>)에서 배열 크기를 지정하지 않도록 방지합니다. 현재 표준에서는 이 생성이 지원되지 않습니다. `make_unique`를 사용하여 배열에 대한 `unique_ptr`을 만드는 경우 배열 요소를 별도로 초기화해야 합니다. 이 오버로드를 고려하는 경우 [std::vector](../standard-library/vector-class.md)를 사용하는 것이 더 나을 수 있습니다.  
  
 `make_unique`는 예외 안전성을 위해 신중하게 구현되기 때문에 `make_unique` 생성자를 직접 호출하는 대신 `unique_ptr`를 사용할 것을 추천합니다.  
  
### <a name="example"></a>예  
  다음 예제에서는 `make_unique`을 사용하는 방법을 보여 줍니다. 더 많은 예제는 [방법: unique_ptr 인스턴스 만들기 및 사용](../cpp/how-to-create-and-use-unique-ptr-instances.md)을 참조하세요.  
  
 [!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]  
  
  `unique_ptr`과 관련하여 오류 C2280이 표시되는 경우 대부분 삭제된 함수인 해당 복사 생성자를 호출하려고 했기 때문입니다.  
  
##  <a name="owner_less"></a>  owner_less  
 공유된 포인터와 약한 포인트에 대한 소유권 기반의 혼합된 비교를 허용합니다. 멤버 함수 `owner_before`에 의해 왼쪽 매개 변수가 오른쪽 매개 변수보다 먼저 순서 지정된 경우 `true`를 반환합니다.  
  
```  
template <class Type>  
struct owner_less; // not defined  
 
template <class Type>  
struct owner_less<shared_ptr<Type>> {  
    bool operator()(
    const shared_ptr<Type>& left,  
    const shared_ptr<Type>& right);

    bool operator()(
    const shared_ptr<Type>& left,  
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,  
    const shared_ptr<Type>& right);
};  
 
template <class Type>  
struct owner_less<weak_ptr<Type>>  
    bool operator()(
    const weak_ptr<Type>& left,  
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,  
    const shared_ptr<Ty>& right);

    bool operator()(
    const shared_ptr<Type>& left,  
    const weak_ptr<Type>& right);
};  
```  
  
### <a name="parameters"></a>매개 변수  
 `_left`  
 공유 또는 약한 포인터입니다.  
  
 `right`  
 공유 또는 약한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 클래스는 모든 멤버 연산자를 `left.owner_before(right)`를 반환하는 것으로 정의합니다.  
  
##  <a name="return_temporary_buffer"></a>  return_temporary_buffer  
 `get_temporary_buffer` 템플릿 함수를 사용하여 할당된 임시 메모리를 취소합니다.  
  
```  
template <class Type>  
void return_temporary_buffer(Type* _Pbuf);
```  
  
### <a name="parameters"></a>매개 변수  
 *_Pbuf*  
 할당을 취소할 메모리에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일시적인 메모리에만 사용해야 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// memory_ret_temp_buf.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   // Create an array of ints  
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300 };  
   int count = sizeof ( intArray ) / sizeof ( int );  
   cout << "The number of integers in the array is: "   
         << count << "." << endl;  
  
   pair<int *, ptrdiff_t> resultPair;  
   resultPair = get_temporary_buffer<int>( count );  
  
   cout << "The number of elements that the allocated memory\n"  
         << " could store is given by: resultPair.second = "   
         << resultPair.second << "." << endl;  
  
   int* tempBuffer = resultPair.first;  
  
   // Deallocates memory allocated with get_temporary_buffer  
   return_temporary_buffer ( tempBuffer );  
}  
```  
  
```Output  
The number of integers in the array is: 7.  
The number of elements that the allocated memory  
 could store is given by: resultPair.second = 7.  
```  
  
##  <a name="static_pointer_cast"></a>  static_pointer_cast  
 shared_ptr로 정적 캐스팅합니다.  
  
```  
template <class Ty, class Other>  
shared_ptr<Ty>  
static_pointer_cast(const shared_ptr<Other>& sp);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 반환된 공유 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 인수 공유 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 인수 공유 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `sp`가 빈 `shared_ptr` 개체인 경우 템플릿 함수는 빈 shared_ptr 개체를 반환합니다. 그러지 않은 경우 `sp`가 소유하는 리소스를 소유하는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md)`<Ty>` 개체를 반환합니다. `static_cast<Ty*>(sp.get())` 식이 유효해야 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__memory__static_pointer_cast.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
struct base   
{   
    int val;   
};   
  
struct derived   
    : public base   
{   
};   
  
int main()   
{   
    std::shared_ptr<base> sp0(new derived);   
    std::shared_ptr<derived> sp1 =   
        std::static_pointer_cast<derived>(sp0);   
  
    sp0->val = 3;   
    std::cout << "sp1->val == " << sp1->val << std::endl;   
  
    return (0);   
}
```  
  
```Output  
sp1->val == 3  
```  
  
##  <a name="swap"></a>  swap(C++ 표준 라이브러리)  
 두 shared_ptr 또는 weak_ptr 개체를 교환합니다.  
  
```  
template <class Ty, class Other>  
void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>  
void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 왼쪽 공유/약한 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 오른쪽 공유/약한 포인터에 의해 제어되는 형식입니다.  
  
 `left`  
 왼쪽 공유/약한 포인터입니다.  
  
 `right`  
 오른쪽 공유/약한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수는 `left.swap(right)`을 호출합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__memory__swap.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```  
  
```Output  
*sp1 == 5  
*sp1 == 10  
*sp1 == 5  
  
*wp1 == 5  
*wp1 == 10  
*wp1 == 5  
```  
  
##  <a name="undeclare_no_pointers"></a>  undeclare_no_pointers  
 기본 주소 포인터와 블록 크기로 정의된 메모리 블록에 있는 문자는 이제 추적이 가능한 포인터를 포함할 수 있음을 가비지 수집기에 알립니다.  
  
```  
void undeclare_no_pointers(
    char* ptr,   
    size_t _Size);
```  
  
### <a name="remarks"></a>설명  
 함수는 모든 가비지 수집기에 알립니다 하는 주소 범위 `[ptr, ptr + _Size)` 이제 추적이 가능한 포인터를 포함할 수 있습니다.  
  
##  <a name="undeclare_reachable"></a>  undeclare_reachable  
 지정된 된 메모리 위치에 대해 선언을 취소합니다.  
  
```  
template <class Type>  
Type *undeclare_reachable(Type* ptr);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|연결할 수 없는 것으로 선언할 메모리 주소에 대한 포인터입니다.|  
  
### <a name="remarks"></a>설명  
 경우 `ptr` 않습니다 `nullptr`, 함수 모든 가비지 수집기에 알립니다 있는 `ptr` 는 더 이상 연결할 수 없습니다. 비교 하는 안전 하 게 파생 된 포인터를 같은 반환 `ptr`합니다.  
  
##  <a name="uninitialized_copy"></a>  uninitialized_copy  
 지정된 소스 범위에서 초기화되지 않은 대상 범위로 개체를 복사합니다.  
  
```  
template <class InputIterator, class ForwardIterator>  
ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 소스 범위에 있는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.  
  
 `last`  
 소스 범위에 있는 마지막 요소를 주소 지정하는 입력 반복기입니다.  
  
 `dest`  
 대상 범위에 있는 첫 번째 요소를 주소 지정하는 정방향 반복기입니다.  
  
### <a name="return-value"></a>반환 값  
 소스 범위는 빈 아닌 경우에 대상 범위를 벗어나는 첫 번째 위치를 주소 지정 하는 정방향 반복기입니다.  
  
### <a name="remarks"></a>설명  
 이 알고리즘을 사용하면 개체 생성에서 메모리 할당을 분리할 수 있습니다.  
  
 템플릿 함수는 다음을 효과적으로 실행합니다.  
  
```cpp  
while (first != last) {  
    new (static_cast<void*>(&* dest++))  
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;  
```  
  
 코드에서 예외를 throw하지 않는 경우 이 경우 생성된 모든 개체가 제거되고 예외가 다시 throw됩니다.  
  
### <a name="example"></a>예  
  
```cpp  
// memory_uninit_copy.cpp  
// compile with: /EHsc /W3  
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
class Integer
{
public:
    Integer(int x) : val(x) {}
    int get() { return val; }
private:
    int val;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    int i;
    cout << "The initialized Array contains " << N << " elements: ";
    for (i = 0; i < N; i++)
    {
        cout << " " << Array[i];
    }
    cout << endl;

    Integer* ArrayPtr = (Integer*)malloc(N * sizeof(int));
    Integer* LArrayPtr = uninitialized_copy(
        Array, Array + N, ArrayPtr);  // C4996  

    cout << "Address of position after the last element in the array is: "
        << &Array[0] + N << endl;
    cout << "The iterator returned by uninitialized_copy addresses: "
        << (void*)LArrayPtr << endl;
    cout << "The address just beyond the last copied element is: "
        << (void*)(ArrayPtr + N) << endl;

    if ((&Array[0] + N) == (void*)LArrayPtr)
        cout << "The return value is an iterator "
        << "pointing just beyond the original array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the original array." << endl;

    if ((void*)LArrayPtr == (void*)(ArrayPtr + N))
        cout << "The return value is an iterator "
        << "pointing just beyond the copied array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the copied array." << endl;

    free(ArrayPtr);

    cout << "Note that the exact addresses returned will vary\n"
        << "with the memory allocation in individual computers."
        << endl;
}
```  
  
##  <a name="uninitialized_copy_n"></a>  uninitialized_copy_n  
 입력 반복기에서 지정된 수의 요소의 복사본을 만듭니다. 복사본은 정방향 반복기에 배치됩니다.  
  
```  
template <class InputIterator, class Size, class ForwardIterator>  
ForwardIterator uninitialized_copy_n(
    InputIterator first,   
    Size count,  
    ForwardIterator dest);
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 복사할 개체를 참조하는 입력 반복기입니다.  
  
 `count`  
 개체를 반복할 횟수를 지정하는 부호 있는 또는 부호 없는 정수 형식입니다.  
  
 `dest`  
 새 복사본의 위치를 참조하는 정방향 반복기입니다.  
  
### <a name="return-value"></a>반환 값  
 대상을 벗어나는 첫 번째 위치를 주소 지정하는 정방향 반복기입니다. 소스 범위는 비어 있으면 반복기 주소 `first`합니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수는 다음을 효과적으로 실행합니다.  
  
```cpp  
    for (; 0 < count; --count)  
        new (static_cast<void*>(&* dest++)) 
            typename iterator_traits<InputIterator>::value_type(*first++);  
    return dest;  
```  
  
 코드에서 예외를 throw하지 않는 경우 이 경우 생성된 모든 개체가 제거되고 예외가 다시 throw됩니다.  
  
##  <a name="uninitialized_fill"></a>  uninitialized_fill  
 지정된 값의 개체를 초기화되지 않은 대상 범위로 복사합니다.  
  
```  
template <class ForwardIterator, class Type>  
void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 시작할 대상 범위에 있는 첫 번째 요소의 주소를 지정하는 정방향 반복기입니다.  
  
 `last`  
 시작할 대상 범위에 있는 마지막 요소의 주소를 지정하는 정방향 반복기입니다.  
  
 `val`  
 대상 범위를 초기화하는 데 사용할 값입니다.  
  
### <a name="remarks"></a>설명  
 이 알고리즘을 사용하면 개체 생성에서 메모리 할당을 분리할 수 있습니다.  
  
 템플릿 함수는 다음을 효과적으로 실행합니다.  
  
```cpp  
while (first != last)  
    new (static_cast<void*>(&* first ++))  
        typename iterator_traits<ForwardIterator>::value_type (val);
```  
  
 코드에서 예외를 throw하지 않는 경우 이 경우 생성된 모든 개체가 제거되고 예외가 다시 throw됩니다.  
  
### <a name="example"></a>예  
  
```cpp  
// memory_uninit_fill.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
class Integer {         // No default constructor  
   public:  
      Integer( int x ) : val( x ) {}  
      int get( ) { return val; }  
   private:  
      int val;  
};  
  
int main( )  
{  
   const int N = 10;  
   Integer val ( 25 );  
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );  
   uninitialized_fill( Array, Array + N, val );  
   int i;  
   cout << "The initialized Array contains: ";  
      for ( i = 0 ; i < N; i++ )  
      {  
         cout << Array [ i ].get( ) << " ";  
      }  
   cout << endl;  
}  
```  
  
```Output  
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25   
```  
  
##  <a name="uninitialized_fill_n"></a>  uninitialized_fill_n  
 지정된 값의 개체를 초기화되지 않은 대상 범위의 지정된 수의 요소로 복사합니다.  
  
```  
template <class FwdIt, class Size, class Type>  
void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `first`  
 초기화할 대상 범위에 있는 첫 번째 요소를 주소 지정하는 정방향 반복기입니다.  
  
 `count`  
 초기화할 요소의 수입니다.  
  
 `val`  
 대상 범위를 초기화하는 데 사용할 값입니다.  
  
### <a name="remarks"></a>설명  
 이 알고리즘을 사용하면 개체 생성에서 메모리 할당을 분리할 수 있습니다.  
  
 템플릿 함수는 다음을 효과적으로 실행합니다.  
  
```cpp  
while (0 < count--)  
    new (static_cast<void*>(&* first++))  
        typename iterator_traits<ForwardIterator>::value_type(val);
```  
  
 코드에서 예외를 throw하지 않는 경우 이 경우 생성된 모든 개체가 제거되고 예외가 다시 throw됩니다.  
  
### <a name="example"></a>예  
  
```cpp  
// memory_uninit_fill_n.cpp  
// compile with: /EHsc /W3  
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
class Integer {   // No default constructor  
public:  
   Integer( int x ) : val( x ) {}  
   int get( ) { return val; }  
private:  
   int val;  
};  
  
int main() {  
   const int N = 10;  
   Integer val ( 60 );  
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );  
   uninitialized_fill_n( Array, N, val );  // C4996  
   int i;  
   cout << "The uninitialized Array contains: ";  
   for ( i = 0 ; i < N; i++ )  
      cout << Array [ i ].get( ) <<  " ";  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<memory>](../standard-library/memory.md)
