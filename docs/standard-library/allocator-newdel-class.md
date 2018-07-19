---
title: allocator_newdel 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dde45090a534fc8d5aff09ee12b1b4fe838d9492
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966278"
---
# <a name="allocatornewdel-class"></a>allocator_newdel 클래스

사용 하는 할당자를 구현 **delete 연산자** 메모리 할당을 취소 하려면 블록 및 **new 연산자** 메모리 블록을 할당 하려면.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Type*|할당자에 의해 할당된 요소 형식입니다.|

## <a name="remarks"></a>설명

합니다 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로로이 클래스를 전달 합니다 *이름* 다음 문에서 매개 변수: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)<br/>
