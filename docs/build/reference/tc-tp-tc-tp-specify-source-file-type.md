---
title: /Tc, /Tp, /TC, /TP (소스 파일 형식 지정) | Microsoft Docs
ms.date: 1/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs:
- C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cb612d5c26fd4db51222c480539867d5e506b70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP(소스 파일 형식 지정)

**/Tc** 옵션 C 소스 파일을 해당 파일 이름 인수 임을.c 확장명이 없는 경우에 지정 합니다. **/Tp** 옵션을 c + + 소스 파일의 파일 이름 인수 임을.cpp 또는.cxx 확장명 없는 경우에 지정 합니다. 옵션 및 파일 이름 사이 공백을 선택 사항입니다. 하나의 파일을 지정 하는 각 옵션 추가 파일을 지정 하려면 옵션을 반복 합니다.

**/TC** 및 **/TP** 의 전역 테스트가 **/Tc** 및 **/Tp**합니다. C 소스 파일로 명령줄의 모든 파일을 처리 하도록 컴파일러에 지정 (**/TC**) 또는 c + + 소스 파일 (**/TP**), 해당 옵션과 관련 된 명령줄에서 위치에 관계 없이 합니다. 방법으로 단일 파일에서 이러한 전역 옵션을 재정의할 수 있습니다 **/Tc** 또는 **/Tp**합니다.

## <a name="syntax"></a>구문

> **/Tc** _filename_  
> **/Tp** _파일 이름_  
> **/TC**  
> **/TP**  

## <a name="arguments"></a>인수

*filename*  
C 또는 c + + 소스 파일.

## <a name="remarks"></a>설명

기본적으로 **CL** .c 확장명을 가진 파일은 C 소스 파일 및.cpp 또는.cxx 확장명을 사용 하 여 파일은 c + + 소스 파일을 가정 합니다.

경우 중 하나는 **TC** 또는 **Tc** 옵션을 지정의 사양을 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 옵션은 무시 됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **고급** 속성 페이지.

1. 수정 된 **컴파일** 속성입니다. 선택 **확인** 또는 **적용** 변경 내용을 적용 하려면.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>을 참조하세요.

## <a name="examples"></a>예제

CL 명령줄이 모두 C 소스 파일을 MAIN.c, TEST.prg, 및 COLLATE.prg가 되도록 지정 합니다. CL PRINT.prg 인식 되지 않습니다.

> CL MAIN 합니다. C /TcTEST.PRG /TcCOLLATE.PRG 인쇄 합니다. PRG

CL 명령줄이 지정 된 c + + 파일로 컴파일된 TEST1.c, TEST2.cxx, TEST3.huh, 및 TEST4.o TEST5.z C 파일로 컴파일됩니다입니다.

> CL TEST1 합니다. C TEST2입니다. CXX TEST3 합니다. 멋지지 TEST4 합니다. O /Tc TEST5 합니다. Z /TP

## <a name="see-also"></a>참고자료

[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
