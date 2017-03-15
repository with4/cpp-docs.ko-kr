---
title: "/w, /Wn, /WX, /Wall, /wln, /wdn, /wen, /won(경고 수준) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarningLevel"
  - "VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarnAsError"
  - "VC.Project.VCCLWCECompilerTool.WarnAsError"
  - "/wx"
  - "VC.Project.VCCLWCECompilerTool.WarningLevel"
  - "/wall"
  - "VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors"
  - "/Wv"
  - "/w0"
  - "/w1"
  - "/w2"
  - "/w3"
  - "/w4"
  - "/wd"
  - "/we"
  - "/wo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/w 컴파일러 옵션"
  - "/W0 컴파일러 옵션[C++]"
  - "/W1 컴파일러 옵션[C++]"
  - "/W2 컴파일러 옵션[C++]"
  - "/W3 컴파일러 옵션[C++]"
  - "/W4 컴파일러 옵션[C++]"
  - "/Wall 컴파일러 옵션[C++]"
  - "/wd 컴파일러 옵션[C++]"
  - "/we 컴파일러 옵션[C++]"
  - "/wo 컴파일러 옵션[C++]"
  - "/WX 컴파일러 옵션[C++]"
  - "w 컴파일러 옵션[C++]"
  - "-w 컴파일러 옵션[C++]"
  - "W0 컴파일러 옵션[C++]"
  - "-W0 컴파일러 옵션[C++]"
  - "W1 컴파일러 옵션[C++]"
  - "-W1 컴파일러 옵션[C++]"
  - "W2 컴파일러 옵션[C++]"
  - "-W2 컴파일러 옵션[C++]"
  - "W3 컴파일러 옵션[C++]"
  - "-W3 컴파일러 옵션[C++]"
  - "W4 컴파일러 옵션[C++]"
  - "-W4 컴파일러 옵션[C++]"
  - "Wall 컴파일러 옵션[C++]"
  - "-Wall 컴파일러 옵션[C++]"
  - "경고 수준 컴파일러 옵션"
  - "경고, 오류 컴파일러 옵션"
  - "wd 컴파일러 옵션[C++]"
  - "-wd 컴파일러 옵션[C++]"
  - "we 컴파일러 옵션[C++]"
  - "-we 컴파일러 옵션[C++]"
  - "wo 컴파일러 옵션[C++]"
  - "-wo 컴파일러 옵션[C++]"
  - "WX 컴파일러 옵션[C++]"
  - "-WX 컴파일러 옵션[C++]"
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /w, /Wn, /WX, /Wall, /wln, /wdn, /wen, /won(경고 수준)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 컴파일에 대해 컴파일러에서 경고가 발생하는 방식을 지정합니다.  
  
## 구문  
  
```  
/w  
/Wn  
/WX  
/Wall  
/wln  
/wdn  
/wen  
/won  
```  
  
## 설명  
 사용 가능한 옵션 및 관련 인수는 다음과 같습니다.  
  
|옵션|설명|  
|--------|--------|  
|**\/w**|모든 컴파일러 경고를 해제합니다.|  
|**\/W** `n`|컴파일러에서 생성한 가장 높은 수준의 경고를 지정합니다.  `n`에 대해 유효한 경고 수준의 범위는 0에서 4까지입니다.<br /><br /> -   수준 0은 모든 경고를 해제합니다.<br />-   수준 1은 심각한 경고를 표시합니다.  Level 1 기본 설정은 입니다.<br />-   수준 2는 모든 수준 1 경고와 수준 1보다 덜 심각한 경고를 표시합니다.<br />-   수준 3은 수준 2 경고 모두와 프로덕션 목적으로 권장되는 기타 모든 경고를 표시합니다.<br />-   수준4는 수준3의 모든 경고와 정보를 알려 주는 경고를 표시합니다.  보풀이 없는 형 보다는에이 옵션을 사용 하는 것이 좋습니다.  그러나 새로운 프로젝트의 경우 모든 컴파일에서 `/W4`를 사용하는 것이 가장 좋을 수 있습니다. 모든 경고를 확인하면 찾기 어려운 코드 결함이 발생할 가능성이 최대한 줄어듭니다.|  
|**\/Wall**|\/W4 경고 모두와 \/W4에 포함 되지 않은 모든 경고 표시\-기본적으로 해제 되어 경고 등입니다.  [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.|  
|**\/WX**|모든 컴파일러 경고를 오류로 처리합니다.  새로운 프로젝트의 경우 모든 컴파일에서 **\/WX**를 사용하는 것이 가장 좋을 수 있습니다. 모든 경고를 확인하면 찾기 어려운 코드 결함이 발생할 가능성이 최대한 줄어듭니다.<br /><br /> 링커에  **\/WX**  옵션입니다.  자세한 내용은 [\/WX\(링커 경고를 오류로 처리\)](../../build/reference/wx-treat-linker-warnings-as-errors.md)를 참조하십시오.|  
|**\/w** `ln`|특정 경고에 대한 수준을 지정합니다.  첫 번째 매개 변수는 **\/W**`n`처럼 경고 수준을 설정하고 두 번째 매개 변수는 실제 경고 번호를 의미합니다.<br /><br /> 예를 들어, `/w14326`은 C4326을 수준 1 경고로 생성합니다.|  
|**\/wd** `n`|지정 된 컴파일러 경고를 사용 하지 않습니다  `n` .<br /><br /> 예를 들어, `/wd4326`은 컴파일러 경고 C4326을 사용하지 않습니다.|  
|**\/we** `n`|지정 된 컴파일러 경고를  `n` 에서 오류로 처리합니다.<br /><br /> 예를 들어, `/we4326`은 경고 C4326을 오류로 표시합니다.|  
|**\/wo** `n`|컴파일러에 지정 된 경고에 한 번만  `n`  오류로 보고합니다.<br /><br /> 예를 들어, `/wo4326`은 경고 C4326을 한 번만 보고합니다.|  
  
 **\/w** 옵션 중 하나를 사용하여 미리 컴파일된 헤더를 만든 경우\([\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)\) 미리 컴파일된 헤더를 사용하면\([\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)\) 이러한 동일한 **\/w** 옵션이 다시 적용됩니다.  사용자는 미리 컴파일된 헤더의 **\/w** 설정을 명령줄의 다른 **\/w** 옵션으로 재정의할 수 있습니다.  
  
 소스 코드의 Pragma 지시문은 **\/w** 옵션에 의해 영향을 받지 않습니다.  
  
 또한 [경고](../../preprocessor/warning.md)을 사용하여 컴파일 타임에 보고되는 경고의 수준을 제어할 수도 있습니다.  
  
 [빌드 오류 설명서](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) 경고 및 경고 수준에 설명 하 고 왜 특정 문을 컴파일할 수 없습니다 의도 한 대로 표시 합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  Select **C\/C\+\+**.  
  
3.  **일반** 속성 페이지를 클릭하고 **경고 수준** 또는 **경고를 오류로 처리** 속성을 수정합니다.  
  
4.  **고급** 속성 페이지를 클릭하고 **특정 경고 사용 안 함** 속성을 수정합니다.  
  
5.  나머지 옵션의 경우, **명령줄** 속성 페이지를 클릭하고 **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)