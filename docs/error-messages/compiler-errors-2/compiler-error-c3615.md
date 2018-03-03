---
title: "컴파일러 오류 C3615 | Microsoft Docs"
ms.date: 10/24/2017
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C3615
dev_langs:
- C++
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea5502ee6e66cf3add4a4ff97e4922a66712ed70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3615"></a>컴파일러 오류 C3615

> constexpr 함수 '*함수*' 상수 식이 될 수 없습니다

함수 *함수* 로 평가 될 수 없습니다 `constexpr` 컴파일 타임에 있습니다. 되도록 `constexpr`, 함수는 호출할 수 있습니다. 다른 `constexpr` 함수입니다.

## <a name="example"></a>예

조건에 따라 평가 연산의 왼쪽 피연산자에서 유효 하지 않을 때 올바르게 visual Studio 2017에서 오류가 발생 한 `constexpr` 컨텍스트. Visual Studio 2017 있지만 Visual Studio 2015에 다음 코드를 컴파일합니다.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

이 문제를 해결 하려면 선언 중 하나는 `array::size()` 클라이언트로 작동할 `constexpr` 또는 제거는 `constexpr` 한정자 `f`합니다.