---
title: "컴파일러 오류 C2653 | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2653
dev_langs: C++
helpviewer_keywords: C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f18e3d6210c5d9b9aba4fdfaab296a01d32b6d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2653"></a>컴파일러 오류 C2653

> '*식별자*': 클래스 또는 네임 스페이스 이름이 아닙니다

언어 구문에는 클래스, 구조체, 공용 구조체 또는 여기에 지정 된 네임 스페이스 이름이 필요합니다.

이 오류는 클래스, 구조체, 공용 구조체 또는 범위 연산자 앞에 네임 스페이스 선언 되지 않은 이름을 사용 하는 경우에 발생할 수 있습니다. 이 문제를 해결 하려면 이름을 선언 하거나 사용 하기 전에 이름을 선언 하는 헤더를 포함 합니다.

C2653 정의 하려는 경우 가능한 이기도 한 *복합 네임 스페이스*, 하나 이상의 범위를 중첩 된 네임 스페이스 이름을 포함 하는 네임 스페이스입니다. 복합 네임 스페이스 정의 C + + 17 하기 전에 c + +에서 사용할 수 없습니다. 지정 하는 경우 Visual Studio 2015 업데이트 3 부터는 복합 네임 스페이스는 지원의 [/std:c + + 최신](../../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션입니다. Visual c + + 2017 15.5 버전 부터는 컴파일러 지원 복합 네임 스페이스 정의 때는 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md) 옵션을 지정 합니다.

## <a name="examples"></a>예제

이 샘플에서는 범위 이름 사용 되었지만 선언 되지 C2653 생성 합니다. 컴파일러는 클래스, 구조체, 공용 구조체 또는 범위 연산자 (:) 앞에 네임 스페이스 이름이 필요합니다.

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

이상 표준 C + + 17에 컴파일되지 않은 코드에서 중첩 된 네임 스페이스는 각 중첩 수준에 명시적 네임 스페이스 선언을 사용 해야 합니다.

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
