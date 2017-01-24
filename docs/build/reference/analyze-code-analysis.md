---
title: "/analyze(코드 분석) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnablePREfast"
  - "/analyze"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalOptions"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/analyze 컴파일러 옵션[C++]"
  - "analyze 컴파일러 옵션[C++]"
  - "-analyze 컴파일러 옵션[C++]"
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /analyze(코드 분석)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

코드 분석 및 제어 옵션을 사용합니다.  
  
## 구문  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## 인수  
 \/analyze  
 기본 모드에서 분석을 설정합니다.  분석 출력은 다른 오류 메시지와 같이 **출력** 창으로 이동합니다.  **\/analyze\-**를 사용하여 분석을 명시적으로 해제합니다.  
  
 \/analyze:WX\-  
 **\/analyze:WX\-**를 지정하면 **\/WX**를 사용하여 컴파일할 때 코드 분석 경고를 오류로 취급하지 않습니다.  자세한 내용은 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하십시오.  
  
 \/analyze:log `filename`  
 자세한 분석기 결과는 `filename`이 지정한 파일에 XML로 작성됩니다.  
  
 \/analyze:quiet  
 **출력** 창으로의 분석기 출력을 해제합니다.  
  
 \/analyze:stacksize `number`  
 이 옵션과 사용되는 `number` 매개 변수는 경고 [C6262](../Topic/C6262.md)가 생성되는 스택 프레임의 크기\(바이트\)를 지정합니다.  이 매개 변수가 지정되지 않은 경우 스택 프레임 크기는 기본적으로 16KB입니다.  
  
 \/analyze:max\_paths `number`  
 이 옵션과 사용되는 `number` 매개 변수는 분석할 코드 경로의 최대 수를 지정합니다.  이 매개 변수가 지정되지 않은 경우 숫자는 기본적으로 256입니다.  값이 클수록 더욱 철저한 검사를 수행하지만 분석 시간이 길어질 수 있습니다.  
  
 \/analyze:only  
 일반적으로 컴파일러는 코드를 생성하고 분석기를 실행한 후에 추가 구문 검사를 실시합니다.  **\/analyze:only** 옵션은 이 코드 생성 통과를 해제합니다. 이렇게 하면 분석이 빨라지지만 컴파일러의 코드 생성 통과로 검색된 컴파일 오류 및 경고를 내보내지 않습니다.  프로그램에 코드 생성 오류가 있는 경우 분석 결과가 안정적이지 않을 수 있습니다. 따라서 코드가 이미 오류 없이 코드 생성 구문 검사를 통과하는 경우에만 이 옵션을 사용하는 것이 좋습니다.  
  
## 설명  
 자세한 내용은 [C\/C\+\+용 코드 분석 개요](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) 및 [C\/C\+\+용 코드 분석 경고](../Topic/Code%20Analysis%20for%20C-C++%20Warnings.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **코드 분석** 노드를 확장합니다.  
  
4.  **일반** 속성 페이지를 클릭합니다.  
  
5.  하나 이상의 **코드 분석** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)