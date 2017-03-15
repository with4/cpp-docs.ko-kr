---
title: "/Zo(최적화된 디버깅 향상) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "-Zo"
  - "/Zo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zo 컴파일러 옵션[C++]"
  - "Zo 컴파일러 옵션[C++]"
  - "-Zo 컴파일러 옵션[C++]"
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zo(최적화된 디버깅 향상)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디버그되지 않은 빌드에서 최적화된 코드에 대해 향상된 디버깅 정보를 생성합니다.  
  
## 구문  
  
```cpp  
/Zo[-]  
```  
  
## 설명  
 **\/Zo** 컴파일러 스위치는 최적화된 코드에 대한 향상된 디버깅 정보를 생성합니다.  최적화는 지역 변수에 레지스터를 사용하고 코드를 다시 정렬하며 루프를 벡터화하고 인라인 함수 호출을 수행할 수 있습니다.  이와 같이 최적화를 수행하면 소스 코드와 컴파일된 개체 코드 간 관계가 명확하지 않을 수 있습니다.  **\/Zo** 스위치는 지역 변수 및 인라인된 함수에 대해 추가적인 디버깅 정보를 생성하도록 컴파일러에 지시합니다.  이 경우 Visual Studio 디버거에서 최적화된 코드를 단계별로 실행할 때 **자동**, **지역** 및 **조사식** 창에서 변수를 확인할 수 있습니다.  또한 스택 추적을 설정하여 WinDBG 디버거에 인라인된 함수를 표시할 수도 있습니다.  최적화를 사용하지 않도록 설정한\([\/Od](../../build/reference/od-disable-debug.md)\) 디버그 빌드의 경우 **\/Zo**를 지정할 때 생성된 추가 디버깅 정보가 필요하지 않습니다.  릴리스 구성을 디버그하려면 최적화가 설정된 상태에서 **\/Zo** 스위치를 사용합니다.  최적화 스위치에 대한 자세한 내용은 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)을 참조하세요.  **\/Zi** 또는 **\/Z7**을 사용하여 디버깅 정보를 지정하는 경우 **\/Zo** 옵션은 Visual Studio 2015에서 기본적으로 사용됩니다.  **\/Zo\-**를 지정하여 이 컴파일러 옵션을 명시적으로 사용하지 않도록 설정합니다.  
  
 **\/Zo** 스위치는 Visual Studio 2013 업데이트 3에서 사용할 수 있으며 이전에 문서화되지 않은 **\/d2Zi\+** 스위치를 대신합니다.  
  
### Visual Studio에서 \/Zo 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **구성 속성**, **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **\/Zo**를 포함하도록 `추가 옵션` 속성을 수정한 후 **확인**을 선택합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [편집하며 계속하기](../Topic/Edit%20and%20Continue.md)