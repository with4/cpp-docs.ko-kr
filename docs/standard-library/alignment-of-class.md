---
title: alignment_of 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b679d4c8807a19c977cd7e59481dc1d78e67ba1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956520"
---
# <a name="alignmentof-class"></a>alignment_of 클래스

지정된 형식의 맞춤을 가져옵니다. 이 구조체는 [alignof](../cpp/alignof-and-alignas-cpp.md) 측면에서 구현됩니다. 맞춤 값을 쿼리만 하면 되는 경우 `alignof`를 직접 사용합니다. 태그 디스패치를 수행하는 경우처럼 정수 계열 상수가 필요한 경우 alignment_of를 사용합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>매개 변수

*Ty* 쿼리할 형식입니다.

## <a name="remarks"></a>설명

값을 보유 하는 형식 쿼리 된 형식의 맞춤 *Ty*합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage 클래스](../standard-library/aligned-storage-class.md)<br/>
