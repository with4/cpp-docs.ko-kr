---
title: "-w,-W0,-W1,-W2,-W3,-W4,-w1,-w2,-w3,-w4,-벽,-wd,-we,-wo-Wv,-WX (경고 수준) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
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
dev_langs: C++
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
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f38328f94fd68b3b5402d08ddb6d2bd97e3de76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, / we, /wo /Wv, /WX (경고 수준)
컴파일러가 지정된 컴파일에 대해 경고를 생성하는 방법을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/w  
/W0  
/W1  
/W2  
/W3  
/W4  
/Wall  
/Wv[<version>]  
/WX  
/w1<warning>   
/w2<warning>   
/w3<warning>   
/w4<warning>   
/wd<warning>   
/we<warning>   
/wo<warning>  
```  
  
## <a name="remarks"></a>설명  
 경고 옵션은 컴파일러 경고를 표시 하 고 전체 컴파일에 대 한 경고 동작을 지정합니다.  
  
 경고 옵션 및 관련된 인수는 다음 표에 설명 된:  
  
|옵션|설명|  
|------------|-----------------|  
|**/w**|모든 컴파일러 경고를 표시 하지 않습니다.|  
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|컴파일러에서 생성할 경고 수준을 지정 합니다. 경고 수준의 유효한 범위는 0에서 4 까지입니다.<br /><br /> -   **/W0** 모든 경고를 표시 하지 않습니다.<br />-   **/ W1** 수준 1 (심각한) 경고를 표시 합니다. **/ W1** 기본 설정입니다.<br />-   **/W2** 수준 1 및 수준 2 (중요 한) 경고를 표시 합니다.<br />-   **/W3** 수준 1, 수준 2 및 3 (프로덕션 품질) 경고 수준 표시 됩니다.<br />-   **/W4** 수준 1, 2, 수준 및 수준 3 경고를 표시 하 고 모든 수준 4 (정보) 경고를 기본적으로 해제 되지 않습니다. 이 옵션은 매우 사소한 경고를 제공하기 위해서만 사용하는 것이 좋습니다. 그러나 새 프로젝트를 수 있습니다 사용할 최상의 **/W4** 있으므로 모든 컴파일에서에서 가장 적은 찾기 어려운 코드 결함 이렇게 하면 합니다.|  
|**/Wall**|으로 표시 하는 모든 경고를 표시 **/W4** 및 다른 모든 경고를 **/W4** 포함 되지 않습니다-기본적으로 해제 되어 있는 경고 예를 들어 합니다. 자세한 내용은 참조 [컴파일러 경고 하는 Off By Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)합니다.|  
|**/Wv**`:version`|컴파일러 버전 보다 최신에 도입 된 경고 표시 안 함 `version`합니다. 이전 버전의 컴파일러에서 사용 하는 경우 경고 없이 컴파일되는 코드에서 새로운 경고가 있는지 확인 하 고 수정 하는 동안 빌드 프로세스에서 새 경고를 일시적으로 표시를이 옵션을 사용할 수 있습니다. 선택적 매개 변수 `version` 형식은 `nn`[.`mm` [. `bbbbb`]] 여기서 `nn` 주 버전 번호는 `mm` 선택적 부 버전 번호 및 `bbbbb` 는 컴파일러의 선택적 빌드 번호입니다. 사용 예를 들어 `/Wv:17.00.00000` Visual c + + 2012 이상과 도입 된 경고를 표시 하지 않아도 됩니다. 기본적으로 **/Wv** 사용 하 여 현재 컴파일러 버전 번호 및 경고가 표시 되지 않습니다. 컴파일러 버전에 의해 표시 되지 경고에 대 한 정보를 참조 하십시오. [컴파일러 버전으로 컴파일러 경고](../..//error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)합니다.|  
|**/WX**|모든 컴파일러 경고를 오류로 처리합니다. 새 프로젝트를 사용 하 여 수 **/WX** 있으므로 모든 컴파일에서 가장 적은 찾기 어려운 코드 결함 되도록 모든 경고를 해결 합니다.<br /><br /> 링커에 **/WX** 옵션입니다. 자세한 내용은 [/WX(링커 경고를 오류로 처리)](../../build/reference/wx-treat-linker-warnings-as-errors.md)를 참조하세요.|  
|**/w1**`n`<br /><br /> **/w2**`n`<br /><br /> **/w3**`n`<br /><br /> **/w4**`n`|지정한 경고 번호에 대 한 경고 수준을 설정 `n`합니다. 이렇게 하면 특정 경고 수준을 설정 된 경우 해당 경고에 대 한 컴파일러 동작을 변경할 수 있습니다. 기본 Visual Studio에서 제공 하는 것 보다는 경고에 대 한 고유한 코딩 표준을 적용 하 다른 경고 옵션과 조합 하 여 이러한 옵션을 사용할 수 있습니다.<br /><br /> 예를 들어 `/w34326` 4326 1 수준이 아닌 수준 3 경고로 생성 합니다. 모두 사용 하 여 컴파일하는 경우는 `/w34326` 옵션 및 `/W2` 옵션을 경고 c 4326은 생성 되지 않습니다.|  
|**/wd**`n`|지정 된 컴파일러 경고를 표시 하지 `n`합니다.<br /><br /> 예를 들어 `/wd4326` 컴파일러 경고 c 4326을 표시 하지 않습니다.|  
|**/we**`n`|지정 된 컴파일러 경고 처리 `n` 오류로 서 발생 합니다.<br /><br /> 예를 들어 `/we4326` 경고 번호 c 4326 컴파일러에서 오류로 간주 하면 됩니다.|  
|**/wo**`n`|즉 컴파일러 경고에 지정 된 보고서 `n` 한 번만 합니다.<br /><br /> 예를 들어 `/wo4326` 경고 c 4326을 한 번만 보고, 원인 처음 발견 되는 컴파일러에 의해 합니다.|  
  
 사용 하는 경우 경고 옵션 중 하나를 사용 하 여 미리 컴파일된 헤더를 만들 때는 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션을 사용 하 여 미리 컴파일된 헤더 사용 되는 모든는 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) 옵션을 사용 하면 이러한 동일한 경고 옵션이 적용 하려면 다시 실행 합니다. 명령줄에서 다른 경고 옵션을 사용 하 여 미리 컴파일된 헤더에 설정 된 경고 옵션을 재정의할 수 있습니다.  
  
 사용할 수는 [#pragma 경고](../../preprocessor/warning.md) 즉 경고의 수준을 제어 하는 지시문이 특정 소스 파일에서 컴파일 타임에 보고 합니다.  
  
 소스 코드에서 Pragma 경고 지시문에 의해 영향을 받지 않습니다.는 **/w** 옵션입니다.  
  
 [빌드 오류 설명서](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) 경고 및 경고 수준을 설명 하 고 사용자가 의도적으로 특정 문은 컴파일되지 않을 수 있습니다 이유를 나타냅니다.  
  
### <a name="to-set-the-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 **C/c + +**합니다.  
  
3.  에 **일반** 속성 페이지에서 수정할는 **경고 수준** 또는 **경고를 오류로 처리** 속성입니다.  
  
4.  에 **고급** 속성 페이지에서 수정할는 **특정 경고 사용 안 함** 속성입니다.  
  
5.  나머지 옵션에 **명령줄** 속성 페이지에 컴파일러 옵션을 입력 합니다는 **추가 옵션** 상자입니다.  
  
### <a name="to-set-the-compiler-option-programmatically"></a>프로그래밍 방식으로 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)