---
title: make_signed 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::make_signed
dev_langs:
- C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fe6eb3ffa83316071de2ba26cf80e6e6cbd5245
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957349"
---
# <a name="makesigned-class"></a>make_signed 클래스

형식을 만들거나 형식의 크기보다 크거나 같은 부호가 있는 가장 작은 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

형식 수정자의 인스턴스는 수정 된 형식인 됩니다 *T* 경우 `is_signed<T>` 마찬가지입니다. 그렇지 않은 경우 가장 작은 부호 없는 형식 `UT`이며, 여기서 `sizeof (T) <= sizeof (UT)`입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
