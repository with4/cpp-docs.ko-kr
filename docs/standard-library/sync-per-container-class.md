---
title: "sync_per_container 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c98e8f7524864e5249c08e2b6f3d4a38ea8e4be
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="syncpercontainer-class"></a>sync_per_container 클래스
각 할당자 개체에 대해 별도의 캐시 개체를 제공하는 [동기화 필터](../standard-library/allocators-header.md)를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Cache>  
class sync_per_container
 : public Cache
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Cache`|동기화 필터와 연결된 캐시 형식입니다. [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) 또는 [cache_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[equals](#equals)|두 캐시가 같은지 비교합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="equals"></a>  sync_per_container::equals  
 두 캐시가 같은지 비교합니다.  
  
```
bool equals(const sync_per_container<Cache>& Other) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Cache`|동기화 필터의 캐시 개체입니다.|  
|`Other`|같은지 비교할 캐시 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 구성원 함수는 항상 `false`를 반환합니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)



