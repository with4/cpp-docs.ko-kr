---
title: /Zc:referenceBinding (참조 바인딩 규칙 적용) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30038f6ff73eaa2d9536c3685927458a70209864
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (참조 바인딩 규칙 적용)

경우는 **/Zc:referenceBinding** 옵션을 지정한 경우 컴파일러는 임시 바인딩할 비 const lvalue 참조를 허용 하지 않습니다.

## <a name="syntax"></a>구문

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>설명

경우 **/Zc:referenceBinding** 이 지정 된 경우 컴파일러는 C + + 11 표준의 섹션 8.5.3 뒤에 오는 비 const lvalue 참조에는 사용자 정의 형식을 임시 바인딩하는 식으로 허용 하지 않습니다. 기본적으로 또는 **/Zc:referenceBinding-** 지정 않으면, 컴파일러는 Microsoft 확장으로 이러한 식이 허용 하지만 수준 4 경고가 발생 합니다. 코드 보안, 이식성 및 규칙을 사용 하는 권장 **/Zc:referenceBinding**합니다.

**/Zc:referenceBinding** 옵션은 기본적으로 해제 되어 있습니다. [관대 한 /-](permissive-standards-conformance.md) 컴파일러 옵션에는 암시적으로이 옵션을 설정 하지만 사용 하 여 재정의할 수 있습니다 **/Zc:referenceBinding-** 합니다.

## <a name="example"></a>예제

이 샘플에서는 사용자 정의 형식의 임시 비 const lvalue 참조에 바인딩될 수 있는 Microsoft 확장을 보여 줍니다.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zc:referenceBinding** 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[컴파일러 옵션](../../build/reference/compiler-options.md)<br/>
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)<br/>
[/Zc(규칙)](../../build/reference/zc-conformance.md)<br/>
