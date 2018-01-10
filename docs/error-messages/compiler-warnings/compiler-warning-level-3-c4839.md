---
title: "컴파일러 경고 (수준 3) C4839 | Microsoft Docs"
ms.date: 10/25/2017
ms.technology: cpp-tools
ms.topic: error-reference
f1_keywords: C4839
dev_langs: C++
helpviewer_keywords: C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aee1e564ffd72b9b08d883c94311c2bca72b5aef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4839"></a>컴파일러 경고 (수준 4) C4839

> 클래스의 비표준 사용*형식*' variadic 함수에 대 한 인수로

Visual Studio 2017 클래스 또는 구조체는 variadic에 전달 되는 함수에서 같은 `printf` 일반적으로 복사할 수 여야 합니다. 해당 개체를 전달할 때 컴파일러는 비트 복사본을 만들기만 하고 생성자 또는 소멸자를 호출하지 않습니다.

## <a name="example"></a>예

다음 샘플에서는 C4839 오류가 생성 됩니다.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

오류를 수정하려면 일반적으로 복사 가능한 형식을 반환하는 멤버 함수를 호출하거나

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

정적 캐스트를 수행하여 개체를 변환한 후 전달합니다.

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

빌드 및 관리를 사용 하 여 문자열에 대 한 `CStringW`, 제공 된 `operator LPCWSTR()` 캐스팅을 사용해는 `CStringW` 개체를 형식 문자열에 필요한 C 포인터입니다.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```