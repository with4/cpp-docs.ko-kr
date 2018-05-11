---
title: char_traits&lt;wchar_t&gt; 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a117a7f9299591d971ecbfdd0a681b008937da33
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="chartraitsltwchartgt-struct"></a>char_traits&lt;wchar_t&gt; 구조체

`wchar_t` 형식 요소에 대한 템플릿 구조체 **char_traits\<CharType>** 의 특수화인 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>설명

특수화를 사용하면 구조체에서 이 `wchar_t` 형식의 개체를 조작하는 라이브러리 함수를 활용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<string>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[char_traits 구조체](../standard-library/char-traits-struct.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
