---
title: char_traits&lt;char16_t&gt; 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24d6c3d5dd11290ce4151b5d54885ba492b8ee45
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845286"
---
# <a name="chartraitsltchar16tgt-struct"></a>char_traits&lt;char16_t&gt; 구조체

`char16_t` 형식 요소에 대한 템플릿 구조체 **char_traits\<CharType>** 의 특수화인 구조체입니다.

## <a name="syntax"></a>구문

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>설명

특수화를 사용하면 구조체에서 `char16_t` 형식의 개체를 조작하는 라이브러리 함수를 활용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<string>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<string>](../standard-library/string.md)<br/>
[char_traits 구조체](../standard-library/char-traits-struct.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
