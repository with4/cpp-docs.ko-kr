---
title: discard_block_engine 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b65cfbe156ba462af9e87abf82d63023cfdc44b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957440"
---
# <a name="discardblockengine-class"></a>discard_block_engine 클래스

기본 엔진에서 반환된 값을 버려 임의의 시퀀스를 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>매개 변수

*엔진* 기본 엔진 유형입니다.

*P* **블록 크기**합니다. 각 블록에 있는 값의 수입니다.

*R* **사용된 된 블록**합니다. 사용된 각 블록에 있는 값의 수입니다. 나머지는 버립니다 (`P` - `R`). **사전 조건**: `0 < R ≤ P`

## <a name="members"></a>멤버

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

엔진 구성원에 대한 자세한 내용은 [\<random>](../standard-library/random.md)을 참조하세요.

## <a name="remarks"></a>설명

이 템플릿 클래스는 기본 엔진에서 반환하는 일부 값을 버려 값을 생성하는 엔진 어댑터에 대해 설명합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<random>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<random>](../standard-library/random.md)<br/>
