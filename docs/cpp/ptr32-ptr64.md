---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39078cfef6b327aee60d98fce6cccc0b69c5953b
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941706"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft 전용**

**__ptr32** 32 비트 시스템에서 네이티브 포인터를 나타내는 동안 **__ptr64** 64 비트 시스템에서 네이티브 포인터를 나타냅니다.

다음 예제에서는 이러한 포인터 형식 각각을 선언하는 방법을 보여 줍니다.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

 32 비트 시스템에서 사용 하 여 포인터 선언 **__ptr64** 32 비트 포인터로 잘립니다. 64 비트 시스템에서 사용 하 여 포인터 선언 **__ptr32** 64 비트 포인터로 강제 변환 됩니다.

> [!NOTE]
> 사용할 수 없습니다 **__ptr32** 또는 **__ptr64** 사용 하 여 컴파일하면 **/clr: pure**합니다. 그렇지 않으면 컴파일러 오류 C2472 생성 됩니다. **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

## <a name="example"></a>예

다음 예제에는 선언 및 사용 하 여 포인터를 할당 하는 방법을 보여 줍니다 합니다 **__ptr32** 하 고 **__ptr64** 키워드입니다.

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

- [기본 형식](../cpp/fundamental-types-cpp.md)