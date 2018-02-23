---
title: "-w,-W0,-W1,-W2,-W3,-W4,-w1,-w2,-w3,-w4,-벽,-wd,-we,-wo-Wv,-WX (경고 수준) | Microsoft Docs"
ms.custom: 
ms.date: 01/31/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
dev_langs:
- C++
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee6ac53bd92873279c08dc7458114612d00ff791
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, / we, /wo /Wv, /WX (경고 수준)

컴파일러가 지정된 컴파일에 대해 경고를 생성하는 방법을 지정합니다.

## <a name="syntax"></a>구문

> **/w**  
> **/W0**  
> **/W1**  
> **/W2**  
> **/W3**  
> **/W4**  
> **/Wall**  
> **/Wv**\[**:**_version_]  
> **/WX**  
> **/w1**_warning_  
> **/w2**_warning_  
> **/w3**_warning_  
> **/w4**_warning_  
> **/wd**_warning_  
> **/we**_warning_  
> **/wo**_warning_  

## <a name="remarks"></a>설명

경고 옵션은 컴파일러 경고를 표시 하 고 전체 컴파일에 대 한 경고 동작을 지정합니다.

경고 옵션 및 관련된 인수는 다음 표에 설명 된:

|옵션|설명|
------------|-----------------|
|**/w**|모든 컴파일러 경고를 표시 하지 않습니다.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|컴파일러에서 생성할 경고 수준을 지정 합니다. 경고 수준의 유효한 범위는 0에서 4 까지입니다.<br />**/W0** 모든 경고를 표시 하지 않습니다. 이에 해당 하는 **/w**합니다.<br />**/ W1** 수준 1 (심각한) 경고를 표시 합니다. **/ W1** 명령줄 컴파일러의 기본 설정입니다.<br />**/W2** 수준 1 및 수준 2 (중요 한) 경고를 표시 합니다.<br />**/W3** 수준 1, 수준 2 및 3 (프로덕션 품질) 경고 수준 표시 됩니다. **/W3** IDE에서 기본 설정입니다.<br />**/W4** 수준 1, 2, 수준 및 수준 3 경고를 표시 하 고 모든 수준 4 (정보) 경고를 기본적으로 해제 되지 않습니다. 이 옵션을 사용 하 여 사소한 경고를 제공 하는 것이 좋습니다. 새 프로젝트를 사용 하 여 수 **/W4** 있으므로 모든 컴파일에서에서 가장 적은 찾기 어려운 코드 결함 이렇게 하면 합니다.|
|**/Wall**|으로 표시 하는 모든 경고를 표시 **/W4** 및 다른 모든 경고를 **/W4** 포함 되지 않습니다-기본적으로 해제 되어 있는 경고 예를 들어 합니다. 자세한 내용은 참조 [컴파일러 경고 하는 Off By Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)합니다.|
|**/Wv**\[**:**_version_]|컴파일러 버전에 도입 된 경고만 표시 *버전* 및 이전 버전입니다. 컴파일러의 최신 버전으로 마이그레이션할 때 코드에서 새 경고를 표시 하 고 동안 유지 하기 위해 기존 빌드 프로세스 문제를 해결할 때이 옵션을 사용할 수 있습니다. 선택적 매개 변수 *버전* 형식은  *nn* [. *mm*[. *bbbbb*]] 여기서  *nn*  주 버전 번호는 *mm* 선택적 부 버전 번호 및 *bbbbb* 는 컴파일러의 선택적 빌드 번호입니다. 사용 예를 들어 */Wv:17* Visual Studio 2012 (즉, 17의 주 버전 번호에는 컴파일러의 모든 버전)에서 또는 이전 버전에서 도입 된 경고를 표시 하 고 Visual Studio 2013 (주 버전에에서 도입 된 경고 표시 안 함 18) 이상. 기본적으로 **/Wv** 사용 하 여 현재 컴파일러 버전 번호 및 경고가 표시 되지 않습니다. 컴파일러 버전에 의해 표시 되지 경고에 대 한 정보를 참조 하십시오. [컴파일러 버전으로 컴파일러 경고](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)합니다.|
|**/WX**|모든 컴파일러 경고를 오류로 처리합니다. 새 프로젝트를 사용 하 여 수 **/WX** 있으므로 모든 컴파일에서 가장 적은 찾기 어려운 코드 결함 되도록 모든 경고를 해결 합니다.<br /><br /> 링커에 **/WX** 옵션입니다. 자세한 내용은 [/WX(링커 경고를 오류로 처리)](../../build/reference/wx-treat-linker-warnings-as-errors.md)를 참조하세요.|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|지정한 경고 번호에 대 한 경고 수준을 설정  _nnnn_ 합니다. 이렇게 하면 특정 경고 수준을 설정 된 경우 해당 경고에 대 한 컴파일러 동작을 변경할 수 있습니다. 기본 Visual Studio에서 제공 하는 것 보다는 경고에 대 한 고유한 코딩 표준을 적용 하 다른 경고 옵션과 조합 하 여 이러한 옵션을 사용할 수 있습니다.<br /><br /> 예를 들어 **/w34326** 4326 1 수준이 아닌 수준 3 경고로 생성 합니다. 모두 사용 하 여 컴파일하는 경우는 **/w34326** 옵션 및 **/W2** 옵션을 경고 c 4326은 생성 되지 않습니다.|
|**/wd**_nnnn_|지정 된 컴파일러 경고를 표시 하지  _nnnn_ 합니다.<br /><br /> 예를 들어 **/wd4326은** 컴파일러 경고 c 4326을 표시 하지 않습니다.|
|**/we**_nnnn_|지정 된 컴파일러 경고 처리  _nnnn_  오류로 서 발생 합니다.<br /><br /> 예를 들어 **/we4326** 경고 번호 c 4326 컴파일러에서 오류로 간주 하면 됩니다.|
|**/wo**_nnnn_|즉 컴파일러 경고에 지정 된 보고서  _nnnn_  한 번만 합니다.<br /><br /> 예를 들어 **/wo4326** 경고 c 4326을 한 번만 보고, 원인 처음 발견 되는 컴파일러에 의해 합니다.|

사용 하는 경우 경고 옵션 중 하나를 사용 하 여 미리 컴파일된 헤더를 만들 때는 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션을 사용 하 여 미리 컴파일된 헤더 사용 되는 모든는 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) 옵션을 사용 하면 이러한 동일한 경고 옵션이 적용 하려면 다시 실행 합니다. 명령줄에서 다른 경고 옵션을 사용 하 여 미리 컴파일된 헤더에 설정 된 경고 옵션을 재정의할 수 있습니다.

사용할 수는 [#pragma 경고](../../preprocessor/warning.md) 즉 경고의 수준을 제어 하는 지시문이 특정 소스 파일에서 컴파일 타임에 보고 합니다.

소스 코드에서 경고 pragma 지시문에 의해 영향을 받지 않습니다.는 **/w** 옵션입니다.

[빌드 오류 설명서](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) 경고 및 경고 수준을 설명 하 고 사용자가 의도적으로 특정 문은 컴파일되지 않을 수 있습니다 이유를 나타냅니다.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 컴파일러 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 설정 하는 **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, **/wall**m **/Wv**, **/WX** 또는 **/WX-** 옵션을 선택 된 **구성 속성** > **C / C + +** > **일반** 속성 페이지.

   - 설정 하는 **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, 또는 **/wall** 옵션을 수정할 수는 **경고 수준** 속성입니다.

   - 설정 하는 **/WX** 또는 **/WX-** 옵션을 수정할 수는 **경고를 오류로 처리** 속성입니다.

   - 에 대 한 버전을 설정 하는 **/Wv** 옵션을에 컴파일러 버전 번호를 입력의 **경고 버전** 속성입니다.

1. 설정 하는 **/wd** 또는 **/we** 옵션을 선택 된 **구성 속성** > **C/c + +**  >   **고급** 속성 페이지.

   - 설정 하는 **/wd** 옵션을 선택는 **특정 경고 사용 안 함** 속성 컨트롤 드롭다운 선택한 후 **편집**합니다. 편집 상자에는 **특정 경고 사용 안 함** 대화 상자에서 경고 번호를 입력 합니다. 둘 이상의 경고를 입력 하려면 세미콜론을 사용 하 여 값을 구분 (**;**). 예를 들어 입력 C4001 및 C4010 모두를 사용 하지 않으려면 **4001; 4010**합니다. 선택 **확인** 변경 내용을 저장 하 돌아가려면는 **속성 페이지** 대화 상자.

   - 설정 하는 **/we** 옵션을 선택은 **특정 경고를 오류로 처리** 속성 컨트롤 드롭다운 선택한 후 **편집**합니다. 편집 상자에는 **특정 경고를 오류로 처리** 대화 상자에서 경고 번호를 입력 합니다. 둘 이상의 경고를 입력 하려면 세미콜론을 사용 하 여 값을 구분 (**;**). 예를 들어 입력 C4001와 C4010를 오류로 처리할지, **4001; 4010**합니다. 선택 **확인** 변경 내용을 저장 하 돌아가려면는 **속성 페이지** 대화 상자.

1. 설정 하는 **/wo** 옵션을 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지입니다. 입력에 컴파일러 옵션은 **추가 옵션** 상자입니다.

1. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-the-compiler-option-programmatically"></a>프로그래밍 방식으로 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
