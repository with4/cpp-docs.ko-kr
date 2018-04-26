---
title: allocator_suballoc 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
dev_langs:
- C++
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae0783a0fe4042c117a623ab13b2352c2082cbb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorsuballoc-class"></a>allocator_suballoc 클래스

[cache_suballoc](../standard-library/cache-suballoc-class.md) 형식의 캐시를 사용하여 `Type` 형식의 개체에 대한 저장소 할당 및 해제를 관리하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Type`|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로는 다음 문에서 이 클래스를 `name` 매개 변수로서 전달합니다. `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
