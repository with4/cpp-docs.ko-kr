---
title: "rts_alloc 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::rts_alloc
- allocators/stdext::rts_alloc
- rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- rts_alloc class
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
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
ms.openlocfilehash: fe127f896fa902f4a8cdb44454cf6e4c5f449e79
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="rtsalloc-class"></a>rts_alloc 클래스
rts_alloc 템플릿 클래스는 캐시 인스턴스의 배열을 보유하고 컴파일 시간 대신 런타임에 할당 및 할당 취소에 사용할 인스턴스를 결정하는 [filter](../standard-library/allocators-header.md)를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Cache>  
class rts_alloc
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Cache`|배열에 포함된 캐시 인스턴스의 형식입니다. [cache_chunklist Class](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) 또는 [cache_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 템플릿 클래스는 여러 개의 블록 할당자 인스턴스를 보유하고 컴파일 시간 대신 런타임에 할당 또는 할당 취소에 사용할 인스턴스를 결정합니다. rebind를 컴파일할 수 없는 컴파일러에서 사용됩니다.  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[allocate](#allocate)|메모리 블록을 할당합니다.|  
|[deallocate](#deallocate)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[equals](#equals)|두 캐시가 같은지 비교합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="allocate"></a>  rts_alloc::allocate  
 메모리 블록을 할당합니다.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`count`|할당할 배열의 요소 수입니다.|  
  
### <a name="return-value"></a>반환 값  
 할당된 개체에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 구성원 함수는 `caches[_IDX].allocate(count)`를 반환합니다. 여기서 인덱스 `_IDX`는 요청한 블록 크기 `count`에 따라 결정되거나, `count`가 너무 크면 cache 개체를 나타내는 `operator new(count)`. `cache`를 반환합니다.  
  
##  <a name="deallocate"></a>  rts_alloc::deallocate  
 지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|저장소에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|  
|`count`|저장소에서 할당을 취소할 개체의 수입니다.|  
  
### <a name="remarks"></a>설명  
 구성원 함수는 `caches[_IDX].deallocate(ptr, count)`를 반환합니다. 여기서 인덱스 `_IDX`는 요청한 블록 크기 `count`에 따라 결정되거나, `count`가 너무 크면 `operator delete(ptr)`를 반환합니다.  
  
##  <a name="equals"></a>  rts_alloc::equals  
 두 캐시가 같은지 비교합니다.  
  
```
bool equals(const sync<_Cache>& _Other) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Cache`|필터와 연결된 캐시 개체입니다.|  
|`_Other`|같은지 비교할 캐시 개체입니다.|  
  
### <a name="remarks"></a>설명  
 결과가 `caches[0].equals(other.caches[0])`이면 `true`이고 그렇지 않으면 `false`입니다. `caches`는 캐시 개체의 배열을 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)   
 [\<allocators>](../standard-library/allocators-header.md)




