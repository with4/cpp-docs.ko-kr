---
title: __func__ | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __func__
dev_langs:
- C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78a249fe5b111c17c29895edcdc3fa5ba2f27a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="func"></a>__func__

**(C + + 11)**  미리 정의 된 식별자 &#95; &#95;func&#95; &#95; 바깥쪽 함수의 정규화 되지 않은 되지 않은 이름을 포함 하는 문자열로 암시적으로 정의 됩니다. &#95;&#95;func&#95; &#95; c + + 표준에서 위임 하 고 Microsoft 확장명이 아닙니다.

## <a name="syntax"></a>구문

```cpp
__func__
```

## <a name="return-value"></a>반환 값

Null 종료 const char 배열을 반환 문자의 함수 이름을 포함 하는 합니다.

## <a name="example"></a>예제

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>요구 사항

C++11