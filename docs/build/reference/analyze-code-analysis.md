---
title: -분석 (코드 분석) | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4893f30bae3b29538c8bead637cb4d083087a57b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376587"
---
# <a name="analyze-code-analysis"></a>/analyze(코드 분석)

코드 분석 및 제어 옵션을 사용합니다.

## <a name="syntax"></a>구문

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>인수

 /analyze  
 기본 모드에서 분석을 설정합니다. 분석 출력 되는지는 **출력** 다른 오류 메시지와 같이 창. 사용 하 여 **/analyze-** 을 명시적으로 분석을 해제 합니다.

 /analyze:WX-  
 지정 **/analyze: WX-** 를 사용 하 여 컴파일할 때 코드 분석 경고 의미를 오류로 처리 되지 않습니다 **/WX**합니다. 자세한 내용은 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)](../../build/reference/compiler-option-warning-level.md)를 참조하세요.

 /analyze:log `filename`  
 자세한 분석기 결과는 `filename`이 지정한 파일에 XML로 작성됩니다.

 /analyze:quiet  
 분석기 출력을 해제는 **출력** 창.

 /analyze:stacksize `number`  
 `number` 이 옵션을 함께 사용 되는 매개 변수는 경고에 대 한 스택 프레임의 바이트 단위로 크기를 지정 [C6262](/visualstudio/code-quality/c6262) 생성 됩니다. 이 매개 변수가 지정되지 않은 경우 스택 프레임 크기는 기본적으로 16KB입니다.

 /analyze:max_paths `number`  
 이 옵션과 사용되는 `number` 매개 변수는 분석할 코드 경로의 최대 수를 지정합니다. 이 매개 변수가 지정되지 않은 경우 숫자는 기본적으로 256입니다. 값이 클수록 더욱 철저한 검사를 수행하지만 분석 시간이 길어질 수 있습니다.

 /analyze:only  
 일반적으로 컴파일러는 코드를 생성하고 분석기를 실행한 후에 추가 구문 검사를 실시합니다. **/analyze:만** 옵션은이 코드 생성 통과 해제; 이렇게 하면 분석이 빨라지지만 있지만 컴파일 오류 및 경고는 컴파일러의 코드 생성 통과 하 여 검색 된 내보내지 않습니다. 프로그램에 코드 생성 오류가 있는 경우 분석 결과가 안정적이지 않을 수 있습니다. 따라서 코드가 이미 오류 없이 코드 생성 구문 검사를 통과하는 경우에만 이 옵션을 사용하는 것이 좋습니다.

 /analyze: 규칙 집합 `<file_path>.ruleset`  
사용자가 직접 만들 수 있는 사용자 지정 규칙 집합을 포함 하 여를 분석 하기 위해 설정 하는 규칙을 지정할 수 있습니다. 이 스위치를 설정 규칙 엔진의 지정 된 규칙 집합 실행 하기 전에 아닌 멤버를 제외 하기 때문에 더 효율적입니다. 스위치를 설정 하지 않은 경우 엔진은 모든 규칙을 확인 합니다.

Visual Studio와 함께 제공 되는 규칙 집합에서 발견 되 **%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule 집합입니다.**

다음 샘플 사용자 지정 규칙 집합 C6001 및 C26494 확인 하는 규칙 엔진을 지시 합니다. 곳으로 있어서이 파일을 배치할 수는 `.ruleset` 확장 하 고 인수에 대 한 전체 경로 제공 합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/analyze: 플러그 인  
코드 분석의 일부로 실행 될 때 지정된 된 PREfast 플러그 인을 수 있습니다. LocalEspC.dll는 동시성 관련 코드 분석을 구현 하는 플러그 인 검사 C261XX 범위 경고가 발생에서 합니다. 예를 들어 [c 26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167)합니다.

LocalEspC.dll를 실행 하려면이 컴파일러 옵션을 사용 하 여: **/analyze: LocalEspC.dll 플러그 인**

CppCoreCheck.dll를 실행 하려면 먼저 개발자 명령 프롬프트에서이 명령을 실행 합니다.

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

다음이 컴파일러 옵션을 사용 하 여: **/analyze: 플러그 인 EspXEngine.dll**합니다.

## <a name="remarks"></a>설명

자세한 내용은 참조 [C/c + + 개요에 대 한 코드 분석](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) 및 [C/c + + 경고에 대 한 코드 분석](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 확장 된 **구성 속성** 노드.

1. 확장 된 **코드 분석** 노드.

1. **일반** 속성 페이지를 클릭합니다.

1. 하나 이상을 수정 된 **코드 분석** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

- [컴파일러 옵션](../../build/reference/compiler-options.md)
- [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)