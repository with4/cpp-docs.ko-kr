---
title: 컴파일러 경고 (수준 3) C4373 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1694c8d15ad65b39a27af8ae5aae02e9c729896
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-warning-level-3-c4373"></a>컴파일러 경고(수준 3) C4373

> '*함수*': 가상 함수 재정의*base_function*', 매개 변수의 const/volatile 한정자만 다른 경우 이전 버전의 컴파일러를 재정의 하지 않았습니다

## <a name="remarks"></a>설명

응용 프로그램은 기본 클래스의 가상 메서드를 재정의하는 파생 클래스의 메서드를 포함하며, 재정의하는 메서드의 매개 변수는 가상 메서드의 매개 변수와 [const](../../cpp/const-cpp.md) 또는 [volatile](../../cpp/volatile-cpp.md) 한정자만 다릅니다. 이 경우 컴파일러는 함수 참조를 기본 클래스나 파생 클래스 중 하나의 메서드에 바인딩해야 합니다.

버전의 Visual Studio 2008 이전 버전의 컴파일러에서는 함수를 기본 클래스의 메서드에 바인딩한 다음 경고 메시지를 실행 합니다. 후속 버전의 컴파일러에서 무시 된 `const` 또는 `volatile` 한정자에 함수를 파생된 클래스의 메서드에 바인딩한 다음 경고 **C4373**합니다. 이 두 번째 동작은 C++ 표준을 준수합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 C4373 경고를 생성합니다. 이 문제를 해결 하려면 동일한 CV 한정자를 사용 하 여 기본 멤버 함수로 재정의 사용할 수도 있고 또는 한 재정의 만들기 원치 않는 지정할 수 있습니다는 파생된 클래스의 함수를 다른 이름입니다.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```