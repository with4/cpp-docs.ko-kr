---
title: "/Od(디버그 비활성화) | Microsoft Docs"
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
  - "/od"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Od 컴파일러 옵션[C++]"
  - "비활성화(디버그) 컴파일러 옵션[C++]"
  - "최적화 비활성화"
  - "빠른 컴파일"
  - "최적화 없음"
  - "Od 컴파일러 옵션[C++]"
  - "-Od 컴파일러 옵션[C++]"
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Od(디버그 비활성화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램의 모든 최적화를 비활성화하여 컴파일 속도를 높입니다.  
  
## 구문  
  
```  
/Od  
```  
  
## 설명  
 이 옵션이 기본값입니다.  **\/Od** 옵션을 사용하면 코드가 이동하지 않으므로 디버깅 프로세스가 간단해집니다.  디버깅 컴파일러 옵션에 대한 자세한 내용은 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **최적화** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md)