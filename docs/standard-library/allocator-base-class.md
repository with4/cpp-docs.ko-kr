---
title: "allocator_base 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocator_base
- allocators/stdext::allocator_base
- stdext::allocator_base
- stdext::allocators::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
dev_langs:
- C++
helpviewer_keywords:
- allocator_base class
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 11e6300d0d625f419e47d5f60f1db175419e3420
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="allocatorbase-class"></a>allocator_base 클래스
동기화 필터에서 사용자 정의 할당자를 만드는 데 필요한 기본 클래스 및 일반 함수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Type, class Sync>  
class allocator_base
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Type`|할당자에 의해 할당된 요소 형식입니다.|  
|`Sync`|할당자에 대한 동기화 정책, 즉 [sync_none 클래스](../standard-library/sync-none-class.md), [sync_per_container 클래스](../standard-library/sync-per-container-class.md), [sync_per_thread 클래스](../standard-library/sync-per-thread-class.md) 또는 [sync_shared 클래스](../standard-library/sync-shared-class.md)입니다.|  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[allocator_base](#allocator_base)|`allocator_base` 형식의 개체를 생성합니다.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[const_pointer](#const_pointer)|할당자에 의해 관리되는 개체 형식에 대한 상수 포인터를 제공하는 형식입니다.|  
|[const_reference](#const_reference)|할당자에 의해 관리되는 개체 형식에 대한 상수 참조를 제공하는 형식입니다.|  
|[difference_type](#difference_type)|할당자에 의해 관리되는 개체 형식에 대한 포인터 값의 차이를 나타낼 수 있는 부호 있는 정수 형식입니다.|  
|[pointer](#pointer)|할당자에 의해 관리되는 개체 형식에 대한 포인터를 제공하는 형식입니다.|  
|[reference](#reference)|할당자에 의해 관리되는 개체 형식에 대한 참조를 제공하는 형식입니다.|  
|[size_type](#size_type)|템플릿 클래스 `allocator_base`의 개체가 할당할 수 있는 시퀀스의 길이를 나타내는 부호 없는 정수 형식입니다.|  
|[value_type](#value_type)|할당자에 의해 관리되는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[_Charalloc](#charalloc)|`char` 형식의 배열에 대한 저장소를 할당합니다.|  
|[_Chardealloc](#chardealloc)|`char` 형식의 요소를 포함하는 배열에 대한 저장소를 해제합니다.|  
|[address](#address)|값이 지정된 개체의 주소를 찾습니다.|  
|[allocate](#allocate)|적어도 지정된 개수의 요소를 저장할 수 있을 만큼 큰 메모리 블록을 할당합니다.|  
|[construct](#construct)|지정된 값으로 초기화된 특정 형식의 개체를 지정된 주소에 생성합니다.|  
|[deallocate](#deallocate)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[destroy](#destroy)|개체가 저장된 메모리 할당을 취소하지 않고 개체 소멸자를 호출합니다.|  
|[max_size](#max_size)|사용 가능한 메모리가 모두 사용되기 전에 allocator 클래스의 개체가 할당할 수 있는 `Type` 형식의 요소 수를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="charalloc"></a>  allocator_base::_Charalloc  
 `char` 형식의 배열에 대한 저장소를 할당합니다.  
  
```
char *_Charalloc(size_type count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`count`|할당할 배열의 요소 수입니다.|  
  
### <a name="return-value"></a>반환 값  
 할당된 개체에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 rebind를 컴파일할 수 없는 컴파일러로 컴파일할 때 컨테이너에 의해 사용됩니다. 동기화 필터의 `allocate` 함수에 대한 호출 결과를 반환하여 사용자 정의 할당자에 대해 `_Charalloc`를 구현합니다.  
  
##  <a name="chardealloc"></a>  allocator_base::_Chardealloc  
 `char` 형식의 요소를 포함하는 배열에 대한 저장소를 해제합니다.  
  
```
void _Chardealloc(void* ptr, size_type count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|저장소에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|  
|`count`|저장소에서 할당을 취소할 개체의 수입니다.|  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 rebind를 컴파일할 수 없는 컴파일러로 컴파일할 때 컨테이너에 의해 사용됩니다. 동기화 필터의 `deallocate` 함수를 호출하여 사용자 정의 할당자에 대해 `_Chardealloc`를 구현합니다. `*this`와 같은지를 비교하여 같은 크기와 형식의 배열 개체를 할당하는 할당자 개체에 대해 `_Charalloc`를 호출함으로써 포인터 ptr이 이미 반환된 상태여야 합니다. `_Chardealloc`은 예외를 throw할 수 없습니다.  
  
##  <a name="address"></a>  allocator_base::address  
 값이 지정된 개체의 주소를 찾습니다.  
  
```
pointer address(reference val);

const_pointer address(const_reference val);
```  
  
### <a name="parameters"></a>매개 변수  
 `val`  
 주소를 검색하는 개체의 const 또는 nonconst 값입니다.  
  
### <a name="return-value"></a>반환 값  
 각각 const 또는 nonconst 값으로 발견된 개체에 대한 const 또는 nonconst 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `&val`을 반환함으로써 사용자 정의 할당자에 대해 구현됩니다.  
  
##  <a name="allocate"></a>  allocator_base::allocate  
 적어도 지정된 개수의 요소를 저장할 수 있을 만큼 큰 메모리 블록을 할당합니다.  
  
```
template <class Other>  
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Nx`|할당할 배열의 요소 수입니다.|  
|`_Hint`|이 매개 변수는 무시됩니다.|  
  
### <a name="return-value"></a>반환 값  
 할당된 개체에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `_Nx == 1`인 경우 멤버 함수는 Type `*` 형식의 동기화 필터의 `allocate` 함수에 대한 호출 결과를 반환하여 사용자 정의 할당자에 대한 메모리 할당을 구현합니다. 아닌 경우 호출 결과를 `operator new(_Nx * sizeof(Type))`으로 반환하여 Type `*` 형식으로 캐스팅합니다.  
  
##  <a name="allocator_base"></a>  allocator_base::allocator_base  
 `allocator_base` 형식의 개체를 생성합니다.  
  
```
allocator_base();

template <class Other>  
allocator_base(const allocator_base<Other, Sync>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|복사할 할당자 개체입니다.|  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 [allocator_base](../standard-library/allocator-base-class.md) 인스턴스를 생성합니다. 두 번째 생성자는 임의의 `allocator_base<Type, _Sync>` 인스턴스 `a`, `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`에 대해 `allocator_base` 인스턴스를 생성합니다.  
  
##  <a name="const_pointer"></a>  allocator_base::const_pointer  
 할당자에 의해 관리되는 개체 형식에 대한 상수 포인터를 제공하는 형식입니다.  
  
```
typedef const Type *const_pointer;
```  
  
##  <a name="const_reference"></a>  allocator_base::const_reference  
 할당자에 의해 관리되는 개체 형식에 대한 상수 참조를 제공하는 형식입니다.  
  
```
typedef const Type& const_reference;
```  
  
##  <a name="construct"></a>  allocator_base::construct  
 지정된 값으로 초기화된 특정 형식의 개체를 지정된 주소에 생성합니다.  
  
```
void construct(pointer ptr, const Type& val);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|개체를 생성할 위치에 대한 포인터입니다.|  
|`val`|생성되는 개체를 초기화할 값입니다.|  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `new((void*)ptr Type(val)`을 호출함으로써 사용자 정의 할당자에 대해 구현됩니다.  
  
##  <a name="deallocate"></a>  allocator_base::deallocate  
 지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.  
  
```
void deallocate(pointer ptr, size_type _Nx);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|저장소에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|  
|`_Nx`|저장소에서 할당을 취소할 개체의 수입니다.|  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `_Nx == 1`인 경우 동기화 필터 `Sync`에서 `deallocate(ptr)`를 호출하고, 아닌 경우 `operator delete(_Nx * ptr)`를 호출함으로써 사용자 정의 할당자에 대해 구현됩니다.  
  
##  <a name="destroy"></a>  allocator_base::destroy  
 개체가 저장된 메모리 할당을 취소하지 않고 개체 소멸자를 호출합니다.  
  
```
void destroy(pointer ptr);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|소멸될 개체의 주소를 지정하는 포인터입니다.|  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `ptr->~Type()`을 호출함으로써 사용자 정의 할당자에 대해 구현됩니다.  
  
##  <a name="difference_type"></a>  allocator_base::difference_type  
 할당자에 의해 관리되는 개체 형식에 대한 포인터 값의 차이를 나타낼 수 있는 부호 있는 정수 형식입니다.  
  
```
typedef std::ptrdiff_t difference_type;
```  
  
##  <a name="max_size"></a>  allocator_base::max_size  
 사용 가능한 메모리가 모두 사용되기 전에 allocator 클래스의 개체가 할당할 수 있는 `Type` 형식의 요소 수를 반환합니다.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>반환 값  
 할당할 수 있는 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `0 < (size_t)-1 / sizeof(Type)`인 경우 `(size_t)-1 / sizeof(Type)`, 아닌 경우 `1`을 반환함으로써 사용자 정의 할당자에 대해 구현됩니다.  
  
##  <a name="pointer"></a>  allocator_base::pointer  
 할당자에 의해 관리되는 개체 형식에 대한 포인터를 제공하는 형식입니다.  
  
```
typedef Type *pointer;
```  
  
##  <a name="reference"></a>  allocator_base::reference  
 할당자에 의해 관리되는 개체 형식에 대한 참조를 제공하는 형식입니다.  
  
```
typedef Type& reference;
```  
  
##  <a name="size_type"></a>  allocator_base::size_type  
 템플릿 클래스 `allocator_base` 의 개체가 할당할 수 있는 시퀀스의 길이를 나타내는 부호 없는 정수 형식입니다.  
  
```
typedef std::size_t size_type;
```  
  
##  <a name="value_type"></a>  allocator_base::value_type  
 할당자에 의해 관리되는 형식입니다.  
  
```
typedef Type value_type;
```  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




