---
title: "/Qvec-report(자동 벡터화 도우미 보고 수준) | Microsoft Docs"
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
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qvec-report(자동 벡터화 도우미 보고 수준)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러의 보고 기능을 사용 하면 [자동 벡터화](../../parallel/auto-parallelization-and-auto-vectorization.md) 컴파일하는 동안 정보 메시지가 출력 수준을 지정 합니다.  
  
## 구문  
  
```  
/Qvec-report:{1}{2}  
```  
  
## 설명  
 **\/Qvec\-report:1**  
 벡터화 된 루프에 대 한 정보 메시지를 출력 합니다.  
  
 **\/Qvec\-report:2**  
 하 여 벡터화 된 루프와 for 루프는 없는 여 벡터화 된, 이유 코드와 함께 하는 정보 메시지를 출력 합니다.  
  
 이유, 코드 및 메시지에 대한 자세한 내용은 [벡터화 도우미 및 병렬화 도우미 메시지](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)를 참조하십시오.  
  
### Visual Studio에서 \/Qvec\-report 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **속성 페이지** 대화 상자 **C\/c \+ \+**에서 **명령줄**을 선택하세요.  
  
3.  **추가 옵션** 상자에 입력 합니다 `/Qvec-보고서: 1` 또는 `/Qvec-보고서: 2`을 입력합니다.  
  
### 프로그래밍 \/Qvec 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용하십시오.  
  
## 참고 항목  
 [\/Q 옵션\(하위 수준 작업\)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [네이티브 코드의 병렬 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=263662)