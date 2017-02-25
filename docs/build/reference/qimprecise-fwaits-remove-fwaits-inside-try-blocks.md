---
title: "/Qimprecise_fwaits(Try 블록 내의 fwait 제거) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Qimprecise_fwaits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qimprecise_fwaits 컴파일러 옵션 (C++)"
  - "-Qimprecise_fwaits 컴파일러 옵션 (C++)"
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qimprecise_fwaits(Try 블록 내의 fwait 제거)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션을 사용할 때 `try` 블록 내의 `fwait` 명령을 제거합니다.  
  
## 구문  
  
```  
/Qimprecise_fwaits  
```  
  
## 설명  
 **\/fp:except**를 함께 지정하지 않은 경우에는 이 옵션이 적용되지 않습니다.  **\/fp:except** 옵션을 지정하면 컴파일러에서는 `try` 블록의 각 코드 줄 주위에 `fwait` 명령을 삽입합니다.  이렇게 하면 컴파일러에서 예외를 생성하는 특정 코드 줄을 확인할 수 있습니다.  **\/Qimprecise\_fwaits**는 내부 `fwait` 명령을 제거하고 `try` 블록 주위의 wait만 남겨 둡니다.  이렇게 하면 성능이 향상되지만 컴파일러에서는 예외를 발생시킨 코드 줄이 아니라 `try` 블록만 확인할 수 있게 됩니다.  
  
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