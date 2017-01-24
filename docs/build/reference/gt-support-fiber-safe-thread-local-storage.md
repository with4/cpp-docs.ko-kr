---
title: "/GT(파이버 안전 스레드 로컬 저장소 지원) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations"
  - "/gt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GT 컴파일러 옵션[C++]"
  - "파이버 안전 정적 스레드 로컬 저장소 컴파일러 옵션[C++]"
  - "GT 컴파일러 옵션[C++]"
  - "-GT 컴파일러 옵션[C++]"
  - "정적 스레드 로컬 저장소 및 파이버 안전"
  - "스레드 지역 저장소"
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GT(파이버 안전 스레드 로컬 저장소 지원)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정적 스레드 로컬 저장소를 사용하여 할당된 데이터\(`__declspec(thread)`을 사용하여 할당된 데이터\)에 대해 파이버 안전을 지원합니다.  
  
## 구문  
  
```  
/GT  
```  
  
## 설명  
 `__declspec(thread)`을 사용하여 선언된 데이터는 TLS\(스레드 로컬 저장소\) 배열을 통해 참조됩니다.  TLS 배열은 각 스레드에 대해 시스템이 유지하고 있는 주소 배열입니다.  이 배열 내의 각 주소에는 스레드 로컬 저장소 데이터가 들어 있습니다.  
  
 파이버란 스택 및 레지스터 컨텍스트로 구성된 간단한 개체로서 다양한 스레드에서 예약하여 사용할 수 있습니다.  파이버는 어느 스레드에서나 실행할 수 있습니다.  파이버는 스왑되거나 다른 스레드에서 나중에 다시 시작될 수 있으므로 TLS 배열의 주소는 캐시되어서는 안 되며 함수 호출 간에 공통 하위 식으로 최적화되어서도 안 됩니다. 자세한 내용은 [\/Og\(전역 최적화\)](../../build/reference/og-global-optimizations.md) 옵션을 참조하십시오.  **\/GT**를 사용하면 이와 같은 최적화를 수행하지 않습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **파이버 안전 최적화 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)