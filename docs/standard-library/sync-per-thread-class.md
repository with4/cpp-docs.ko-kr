---
title: "sync_per_thread 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_per_thread
- stdext::sync_per_thread [C++], allocate
- stdext::sync_per_thread [C++], deallocate
- stdext::sync_per_thread [C++], equals
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 817f52e11a39de64288c4433b5f29c48ae45ca22
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="syncperthread-class"></a>sync_per_thread 클래스
각 스레드에 대해 별도의 캐시 개체를 제공하는 [동기화 필터](../standard-library/allocators-header.md)를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Cache>  
class sync_per_thread
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Cache`|동기화 필터와 연결된 캐시 형식입니다. [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) 또는 [cache_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 `sync_per_thread`를 사용하는 할당자는 특정 스레드에 할당된 블록을 다른 스레드에서 할당 취소할 수 없더라도 비교 결과 같은 항목으로 확인될 수 있습니다. 이러한 할당자 중 하나를 사용할 때는 특정 스레드에 할당된 메모리 블록이 다른 스레드에 표시되면 안 됩니다. 즉, 실제로는 단일 스레드만 이러한 할당자 중 하나를 사용하는 컨테이너에 액세스해야 합니다.  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[allocate](#allocate)|메모리 블록을 할당합니다.|  
|[deallocate](#deallocate)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[equals](#equals)|두 캐시가 같은지 비교합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="allocate"></a>  sync_per_thread::allocate  
 메모리 블록을 할당합니다.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`count`|할당할 배열의 요소 수입니다.|  
  
### <a name="remarks"></a>설명  
 구성원 함수는 현재 스레드에 속하는 캐시 개체에 대한 `cache::allocate(count)` 호출 결과를 반환합니다. 현재 스레드에 대해 캐시 개체가 할당되지 않은 경우에는 먼저 캐시 개체가 할당됩니다.  
  
##  <a name="deallocate"></a>  sync_per_thread::deallocate  
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
 구성원 함수는 현재 스레드에 속하는 캐시 개체에 대해 `deallocate`를 호출합니다. 현재 스레드에 대해 캐시 개체가 할당되지 않은 경우에는 먼저 캐시 개체가 할당됩니다.  
  
##  <a name="equals"></a>  sync_per_thread::equals  
 두 캐시가 같은지 비교합니다.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Cache`|동기화 필터의 캐시 개체입니다.|  
|`Other`|같은지 비교할 캐시 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 현재 스레드에서 `Other` 또는 이 개체에 대해 캐시 개체가 할당되지 않은 경우 `false`입니다. 그렇지 않으면 두 캐시 개체에 `operator==`를 적용한 결과가 반환됩니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




