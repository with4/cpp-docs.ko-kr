---
title: char_traits&lt;wchar_t&gt; 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2b20b72bf92679395b19b2ad6b8ae68143bb6d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
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
