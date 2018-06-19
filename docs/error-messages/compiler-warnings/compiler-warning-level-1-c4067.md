---
title: 컴파일러 경고 (수준 1) C4067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee6b48327e8754f9388e0df8f43009a5be70c97
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255455"
---
# <a name="compiler-warning-level-1-c4067"></a>컴파일러 경고 (수준 1) C4067

> 예기치 않은 토큰이 전처리기 지시문 다음에 줄 바꿈이 필요 합니다.

## <a name="remarks"></a>설명

컴파일러 발견 하 여 전처리기 지시문 다음에서 추가 문자를 무시 합니다. 이 경우에 일반적인 원인은 흩어진 세미콜론 지시문 뒤에 예기치 않은 문자는 발생할 수 있습니다. 주석에서이 경고를 발생 하지 않습니다. **/Za** 컴파일러 옵션을 사용 하면이 경고를 기본값 보다 더 많은 전처리기 지시문에 대 한 합니다.

## <a name="example"></a>예제

```cpp
// C4067a.cpp
// compile with: cl /EHsc /DX /W1 /Za C4067a.cpp
#include <iostream>
#include <string> s     // C4067
#if defined(X);         // C4067
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif;                 // C4067 only under /Za
int main()
{
    std::cout << s << std::endl;
}
```

이 경고를 해결 하려면 흩어진 문자를 삭제 하거나 주석 블록으로 이동 합니다. 제거 하 여 특정 C4067 경고 비활성화 될 수 있습니다는 **/Za** 컴파일러 옵션입니다.

```cpp
// C4067b.cpp
// compile with: cl /EHsc /DX /W1 C4067b.cpp
#include <iostream>
#include <string>
#if defined(X)
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif
int main()
{
    std::cout << s << std::endl;
}
```