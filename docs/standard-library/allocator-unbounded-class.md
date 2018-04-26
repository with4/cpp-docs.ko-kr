---
title: allocator_unbounded 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
dev_langs:
- C++
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9dbc7fff1d75e683ee36042e852ced68e82ec9dc
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorunbounded-class"></a>allocator_unbounded 클래스

[max_unbounded](../standard-library/max-unbounded-class.md)에 의해 관리되는 길이와 함께 [cache_freelist](../standard-library/cache-freelist-class.md) 형식의 캐시를 사용하여 `Type` 형식의 개체에 대한 저장소 할당 및 해제를 관리하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Type`|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로는 다음 문에서 이 클래스를 `name` 매개 변수로서 전달합니다. `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
