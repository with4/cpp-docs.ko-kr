---
title: '-Zc: noexceptTypes (C + + 17 noexcept 규칙) | Microsoft Docs'
ms.date: 11/14/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:noexceptTypes
dev_langs:
- C++
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25ad2a662af2cda49e3e8dd8c769fa75dafee94b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379551"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (C + + 17 noexcept 규칙)

표준 C + + 17 하면 `throw()` 별칭으로 `noexcept`, 제거 `throw(<type list>)` 및 `throw(...)`, 특정 종류를 포함 하도록이 가능 `noexcept`합니다. C + + 14 이하로 준수 하는 코드에서 다양 한 원본 호환성 문제가 발생할 수 있습니다. **/Zc:noexceptTypes** 옵션 C + + 17 모드에서 코드를 컴파일하면 C + + 14 및 이전 동작을 허용 하거나 표준 C + + 17에 규칙을 지정할 수 있습니다.

## <a name="syntax"></a>구문

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>설명

경우는 **/Zc:noexceptTypes** 옵션을 지정한 경우 컴파일러는 C + + 17 표준에 맞는 하며 처리 [throw ()](../../cpp/exception-specifications-throw-cpp.md) 별칭으로 [noexcept](../../cpp/noexcept-cpp.md), 제거`throw(<type list>)`및 `throw(...)`를 포함 하도록 특정 종류 가능 `noexcept`합니다. **/Zc:noexceptTypes** 옵션은만 사용할 수 있는 경우 [/std:c + + 17](std-specify-language-standard-version.md) 또는 [/std:latest](std-specify-language-standard-version.md) 를 사용할 수 있습니다. **/Zc:noexceptTypes** ISO C + + 17 표준에 맞게 기본적으로 사용 됩니다. [관대 한 /-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/Zc:noexceptTypes**합니다. 이 옵션을 지정 하 여 해제 **/Zc:noexceptTypes-** 의 C + + 14 동작으로 되돌리려면 `noexcept` 때 **/std::C + + 17** 또는 **/std::latest** 지정 됩니다.

Visual Studio 2017 15.5 버전부터, c + + 컴파일러 진단 C + + 17 모드의 선언에 더 많은 일치 하지 않는 예외 사양 시기는 [관대 한 /-](permissive-standards-conformance.md) 옵션을 지정 합니다.

이 예제에서는 예외 지정자로 선언 될 때의 동작 방법을 보여 줍니다.는 **/Zc:noexceptTypes** 옵션을 설정 하거나 사용 하지 않도록 설정 합니다. 동작으로 설정 하면 사용 하 여 컴파일할 `cl /EHsc /W4 noexceptTypes.cpp`합니다. 사용 하지 않도록 설정 하는 경우 동작을 표시 하려면 사용 하 여 컴파일할 `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`합니다.

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

기본 설정을 사용 하 여 컴파일할 때 **/Zc:noexceptTypes**, 샘플 나열 된 경고를 생성 합니다. 코드를 업데이트 하려면 다음 대신 사용 합니다.

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zc:noexceptTypes** 또는 **/Zc:noexceptTypes-** 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](../../build/reference/zc-conformance.md)  
[noexcept](../../cpp/noexcept-cpp.md)  
[예외 사양(throw)](../../cpp/exception-specifications-throw-cpp.md)  
