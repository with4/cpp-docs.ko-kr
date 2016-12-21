---
title: "/Qfast_transcendentals(빠른 초월수 강제 적용) | Microsoft Docs"
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
  - "/Qfast_transcendentals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qfast_transcendentals"
  - "빠른 초월수 강제 적용"
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qfast_transcendentals(빠른 초월수 강제 적용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초월수 함수에 대한 인라인 코드를 생성합니다.  
  
## 구문  
  
```  
/Qfast_transcendentals  
```  
  
## 설명  
 이 컴파일러 옵션은 초월수 함수를 인라인 코드로 강제로 변환하여 실행 속도를 높입니다.  이 옵션은 **\/fp:except**나 **\/fp:precise**와 함께 사용할 때만 적용됩니다.  **\/fp:fast** 아래에서는 초월수 함수의 인라인 코드를 생성하는 것이 이미 기본 동작입니다.  
  
 이 옵션은 **\/fp:strict**와 호환되지 않습니다.  부동 소수점 컴파일러 옵션에 대한 자세한 내용은 [\/fp\(부동 소수점 동작 지정\)](../../build/reference/fp-specify-floating-point-behavior.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/Q 옵션\(하위 수준 작업\)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)