---
title: 컴파일러 경고 (수준 1 및 수준 4) C4700 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 876ae98fb2fdea5a9d8bdaecb93b8c229213d329
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286070"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>컴파일러 경고(수준 1 및 수준 4) C4700

> 초기화 되지 않은 지역 변수 '*이름*' 사용

지역 변수 *이름* 되었습니다 *사용*에서 즉, 읽기, 생기기 전에 값이 할당 되었습니다. C 및 c + +에서 기본적으로 로컬 변수가 초기화 되지 됩니다. 초기화 되지 않은 변수에는 어떤 값도 포함 될 수 있습니다 및 용도 따라 정의 되지 않은 동작이 있습니다. 경고 C4700 거의 항상 프로그램에서 예기치 않은 결과 나 충돌이 시킬 수 있는 버그를 나타냅니다.

이 문제를 해결 하려면 선언 될 때 지역 변수를 초기화할 수도 있고 사용 하기 전에 값을 할당할 수 있습니다. 해당 주소 포인터 매개 변수로 전달 되는 경우 또는 참조 매개 변수로 전달 되는 변수를 초기화 함수를 사용할 수 있습니다.

## <a name="example"></a>예제

이 샘플에서는 초기화 되 고 발생할 수 있는 가비지 값의 종류를 보여 줍니다. 하려면 먼저 변수 t, u 및 v 사용 될 때 C4700를 생성 합니다. 변수 x, y 및 z 사용 하기 전에 초기화 되기 때문에 경고를 발생 하지 수행:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

이 코드의 실행, t, u 및 v는 때를, 초기화 되지 않은 하 고 s에 대 한 출력을 예측할 수 없는:

```Output
Value in s: 37816963
Value in w: 42
```
