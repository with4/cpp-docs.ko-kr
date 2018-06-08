---
title: /Gd, /Gr, /Gv, /Gz (호출 규칙) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gr
- /Gv
- /gz
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
dev_langs:
- C++
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3da8b4fcddbc384a785b27f0a7d706236a46ccf0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703774"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz(호출 규칙)
이러한 옵션은 함수에서 인수는 스택에 밀어 넣은, 여부는 호출자가 함수 또는 호출된 된 함수 호출의 끝에 스택에서 인수를 제거 하는 순서 및 컴파일러를 사용 하 여 식별 이름을 데코 레이트 규칙 결정 개별 함수입니다.

## <a name="syntax"></a>구문

> **/Gd**<br/>
> **/Gr**<br/>
> **/Gv**<br/>
> **/Gz**<br/>

## <a name="remarks"></a>설명

**/Gd**, 기본 설정 지정는 [__cdecl](../../cpp/cdecl.md) 함수 및 표시 된 함수 c + + 멤버를 제외한 모든 함수에 대 한 호출 규칙 [__stdcall](../../cpp/stdcall.md), [__ fastcall](../../cpp/fastcall.md), 또는 [__vectorcall](../../cpp/vectorcall.md)합니다.

**/Gr** 지정는 `__fastcall` 함수 라는 c + + 멤버 함수를 제외한 모든 함수에 대 한 호출 규칙을 `main`, 및 표시 된 함수 `__cdecl`, `__stdcall`, 또는 `__vectorcall`합니다. 모든 `__fastcall` 함수 프로토타입이 있어야 합니다. 이 호출 규칙은 x86, 대상 컴파일러에서 사용할 수 있으며 다른 아키텍처를 대상으로 하는 컴파일러에서 무시 됩니다.

**/Gz** 지정는 `__stdcall` 함수 라는 c + + 멤버 함수를 제외한 모든 함수에 대 한 호출 규칙을 `main`, 및 표시 된 함수 `__cdecl`, `__fastcall`, 또는 `__vectorcall`합니다. 모든 `__stdcall` 함수 프로토타입이 있어야 합니다. 이 호출 규칙은 x86, 대상 컴파일러에서 사용할 수 있으며 다른 아키텍처를 대상으로 하는 컴파일러에서 무시 됩니다.

**/Gv** 지정는 `__vectorcall` 함수, 명명 된 main 함수 c + + 멤버 함수를 제외한 모든 함수에 대 한 호출 규칙을 한 `vararg` 가변 인수 목록 또는 충돌 하는로 표시 된 함수 `__cdecl`, `__stdcall`, 또는 `__fastcall` 특성입니다. 이 호출 규칙 이상 지 원하는 /arch: sse2 x86 및 x64 아키텍처에서 제공 되 고 ARM 아키텍처를 대상으로 하는 컴파일러에서 무시 됩니다.

가변 개수의 인수를 사용 하는 함수를 표시 해야 `__cdecl`합니다.

**/Gd**, **/Gr**, **/Gv** 및 **/Gz** 와 호환 되지 않는 [/clr: safe](../../build/reference/clr-common-language-runtime-compilation.md) 또는 **/clr: pure**. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

> [!NOTE]
> X86 기본적으로 사용 하 여 프로세서, c + + 멤버 함수 [__thiscall](../../cpp/thiscall.md)합니다.

모든 프로세서를 명시적으로 표시 하는 멤버 함수에 대 한 `__cdecl`, `__fastcall`, `__vectorcall`, 또는 `__stdcall` 해당 아키텍처에서 무시 되지 경우 지정 된 호출 규칙을 사용 합니다. 가변 개수의 인수를 사용 하 여 항상 사용 하는 멤버 함수는 `__cdecl` 호출 규칙입니다.

이러한 컴파일러 옵션은 c + + 메서드 및 함수 이름 데코레이션에 대 한 영향을 주지 않습니다. 로 선언 되지 않은 `extern "C"`, c + + 메서드 및 함수는 다른 이름 장식 구성표를 사용 합니다. 자세한 내용은 참조 [데코 레이트 된 이름](../../build/reference/decorated-names.md)합니다.

호출 규칙에 대 한 자세한 내용은 참조 [호출 규칙](../../cpp/calling-conventions.md)합니다.

## <a name="cdecl-specifics"></a>__cdecl 세부 사항

X86 프로세서에서는 모든 함수 인수는 스택에 전달 오른쪽에서 왼쪽으로 합니다. ARM 및 x64 아키텍처에서는 일부 인수가 레지스터에 의해 전달 되 고 나머지는 오른쪽에서 왼쪽으로 스택에 전달 됩니다. 호출 루틴 스택에서 인수를 꺼냅니다.

C의 경우는 `__cdecl` 명명 규칙 사용 하 여 함수 이름 앞에 밑줄이 ( `_` ); 소문자 변환은 수행 되지 않습니다. 로 선언 되지 않은 `extern "C"`, c + + 함수는 다른 이름 장식 구성표를 사용 합니다. 자세한 내용은 참조 [데코 레이트 된 이름](../../build/reference/decorated-names.md)합니다.

## <a name="fastcall-specifics"></a>__fastcall 세부 사항

일부는 `__fastcall` 함수의 인수가 레지스터에 전달 됩니다 (x86 프로세서, ECX 및 EDX), 나머지는 오른쪽에서 왼쪽으로 스택에 푸시됩니다. 호출된 된 루틴을 반환 하기 전에 이러한 인수는 스택에서 팝 합니다. 일반적으로 **/Gr** 실행 시간을 줄입니다.

> [!NOTE]
> 사용 하는 경우 주의 해야는 `__fastcall` 인라인 어셈블리 언어로 작성 된 모든 함수에 대 한 호출 규칙입니다. 레지스터 사용 컴파일러의 사용을 충돌할 수 있습니다.

C의 경우는 `__fastcall` 명명 규칙 사용 하 여 함수 이름 앞에 at 기호 (`@`) 뒤에 크기 (바이트)에서 함수의 인수에 의해 합니다. 없음 대/소문자 변환은 수행 됩니다. 컴파일러는 명명 규칙에 대 한이 서식 파일을 사용합니다.

`@function_name@number`

사용 하는 경우는 `__fastcall` 명명 규칙을 사용 하 여 표준 포함 파일입니다. 그렇지 않으면 확인 되지 않은 외부 참조를 얻을 수 있습니다.

## <a name="stdcall-specifics"></a>__stdcall 세부 사항

A `__stdcall` 함수 인수는 오른쪽에서 왼쪽으로 스택에 밀어 넣은 및 반환 되기 전에 호출된 된 함수가 스택에서 이러한 인수를 꺼냅니다.

C의 경우는 `__stdcall` 명명 규칙 사용 하 여 함수 이름 앞에 밑줄이 ( `_` ) 뒤에는 at 기호 (@) 및 함수 인수 (바이트)에서의 크기입니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 명명 규칙에 대 한이 서식 파일을 사용합니다.

`_functionname@number`

## <a name="vectorcall-specifics"></a>__vectorcall 세부 사항

A `__vectorcall` 함수의 정수 인수는 값으로 전달, 최대 (x86)에 2 또는 4 (x64)를 사용 하 여 정수를 등록 하 고 6 개의 XMM 최대 등록에 대 한 부동 소수점 벡터 값과 나머지는 오른쪽에서 왼쪽으로 스택에 전달 됩니다. 반환 하기 전에 호출된 된 함수가 스택에서 정리 합니다. 벡터와 반환 값을 부동 소수점 x m m 0에 반환 됩니다.

C의 경우는 `__vectorcall` 명명 규칙에 두 개의 at 기호 (@ @) 및 크기 (바이트)는 함수 인수는 함수 이름을 사용 합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 명명 규칙에 대 한이 서식 파일을 사용합니다.

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)을 참조하세요.

1. 선택 된 **C/c + +** > **고급** 속성 페이지.

1. 수정 된 **호출 규칙** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [컴파일러 옵션](../../build/reference/compiler-options.md)
- [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)
