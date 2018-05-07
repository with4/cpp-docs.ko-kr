---
title: 심각한 오류 C1189 | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 051b7eb965526d12311dfacaeae7a00e4fbe4e75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1189"></a>심각한 오류 C1189

> **\#오류:** *사용자가 제공한 오류 메시지*

## <a name="remarks"></a>설명

C1189에서 생성 되는 `#error` 지시문입니다. 지시문을 코딩 하는 개발자는 오류 메시지의 텍스트를 지정 합니다. 자세한 내용은 참조 [#error 지시문 (C/c + +)](../../preprocessor/hash-error-directive-c-cpp.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C1189 오류가 발생 합니다. 이 샘플에서는 개발자는 사용자 지정 오류 메시지를 때문에 `_WIN32` 식별자에 정의 되어 있지 않습니다.

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>참고자료

[#define 지시문(C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)