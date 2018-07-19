---
title: allocator_variable_size 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46ba5742f6beb308ada7ed64788577768afeac60
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953103"
---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size 클래스

저장소 할당 및 개체 형식에 대 한 해제를 관리 하는 개체를 설명 *형식* 형식의 캐시를 사용 하 여 [cache_freelist](../standard-library/cache-freelist-class.md) 관리 하는 길이가 [max_variable_size](../standard-library/max-variable-size-class.md).

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Type*|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

합니다 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로로이 클래스를 전달 합니다 *이름* 다음 문에서 매개 변수: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
