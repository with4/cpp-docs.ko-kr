---
title: is_rvalue_reference 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acba0f78df8cc537aecd5d2fc33380e4674e5721
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956923"
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference 클래스

형식이 rvalue 참조인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>매개 변수

*Ty* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

이 형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 되는 [rvalue 참조](../cpp/rvalue-reference-declarator-amp-amp.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
