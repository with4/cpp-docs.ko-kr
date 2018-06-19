---
title: allocator_chunklist 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_chunklist
- stdext::allocators [C++], allocator_chunklist
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aaa7b01fe4008089cb8a773fc866d62a269ae717
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850511"
---
# <a name="allocatorchunklist-class"></a>allocator_chunklist 클래스

[cache_chunklist](../standard-library/cache-chunklist-class.md) 유형의 캐시를 사용하여 개체에 대한 저장소 할당 및 해제를 관리하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Type`|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로는 다음 문에서 이 클래스를 `name` 매개 변수로서 전달합니다. `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
