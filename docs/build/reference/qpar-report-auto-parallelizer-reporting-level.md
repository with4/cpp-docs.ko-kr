---
title: "/Qpar-report(자동 병렬화 도우미 보고 수준) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qpar-report(자동 병렬화 도우미 보고 수준)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 [자동 평행화 도우미](../../parallel/auto-parallelization-and-auto-vectorization.md)의 보고 기능을 사용하도록 설정하고 컴파일 중에 출력할 정보 메시지의 수준을 지정합니다.  
  
## 구문  
  
```  
/Qpar-report:{1}{2}  
```  
  
## 설명  
 **\/Qpar\-report:1**  
 평행화되는 루프에 대해 정보 메시지를 출력합니다.  
  
 **\/Qpar\-report:2**  
 평행화되는 루프와 평행화되지 않는 루프 둘 다에 대해 정보 메시지와 이유 코드를 출력합니다.  
  
 메시지는 stdout에 보고됩니다.  정보 메시지가 보고되지 않는 경우에는 코드에 루프가 없거나 평행화되지 않은 루프를 보고하도록 보고 수준을 설정하지 않은 것입니다.  이유 코드 및 메시지에 대한 자세한 내용은 [벡터화 도우미 및 병렬화 도우미 메시지](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)를 참조하세요.  
  
### Visual Studio에서 \/Qpar\-report 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **속성 페이지** 대화 상자의 **C\/C\+\+**에서 **명령줄**을 선택합니다.  
  
3.  **추가 옵션** 상자에 `/Qpar-report:1` 또는 `/Qpar-report:2`를 입력합니다.  
  
### 프로그래밍 방식으로 \/Qpar\-report 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용합니다.  
  
## 참고 항목  
 [\/Q 옵션\(하위 수준 작업\)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [네이티브 코드의 병렬 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=263662)