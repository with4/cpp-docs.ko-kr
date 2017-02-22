---
title: "/Qpar(자동 평행화 도우미) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration"
dev_langs: 
  - "C++"
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Qpar(자동 평행화 도우미)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[자동 Parallelizer](../../parallel/auto-parallelization-and-auto-vectorization.md) 자동으로 코드에서 루프를 병렬화 하는 컴파일러 기능을 가능하게 합니다.  
  
## 구문  
  
```  
/Qpar  
```  
  
## 설명  
 컴파일러는 코드에서 루프 자동 병렬화를 때 계산 다중 프로세서 코어를 통해 확산 됩니다.  컴파일러는 이렇게 수 하 고 해당 병렬 처리 성능이 향상 됩니다 확인 하는 경우에 루프를 병렬화 됩니다.  
  
 `#pragma loop()`  지시문은 특정 루프를 병렬화 하는 최적화를 사용할 수 있습니다.  자세한 내용은 [루프](../../preprocessor/loop.md)을 참조하십시오.  
  
 자동 parallelizer에 대 한 출력 메시지를 사용 하는 방법에 대 한 내용은 [\/Qpar\-report\(자동 병렬화 도우미 보고 수준\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)을 확인하세요.  
  
### Visual Studio에서 \/Qpar 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **속성 페이지** 대화 상자 **C\/c \+ \+**에서 **명령줄**을 선택하세요.  
  
3.  **추가 옵션** 상자에 `/Qpar`을 입력합니다.  
  
### 프로그래밍 방식으로 \/Qpar 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용하십시오.  
  
## 참고 항목  
 [\/Q 옵션\(하위 수준 작업\)](../../build/reference/q-options-low-level-operations.md)   
 [\/Qpar\-report\(자동 병렬화 도우미 보고 수준\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [](../../preprocessor/loop.md "loop")