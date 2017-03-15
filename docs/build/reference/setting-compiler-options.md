---
title: "컴파일러 옵션 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 옵션 설정"
  - "컴파일러 옵션, 설정"
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 옵션 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 및 C\+\+ 컴파일러 옵션은 통합 개발 환경이나 명령줄에서 설정할 수 있습니다.  
  
## 개발 환경에서 설정  
 **속성 페이지** 대화 상자에서 각 프로젝트의 컴파일러 옵션을 설정할 수 있습니다.  왼쪽 창에서 **구성 속성**, **C\/C\+\+**를 선택한 후 컴파일러 옵션 범주를 선택합니다.  각 컴파일러 옵션에 대한 항목에서는 설정하는 방법과 개발 환경의 어느 부분에 있는지 설명합니다.  전체 목록은 [컴파일러 옵션](../../build/reference/compiler-options.md)을 참조하십시오.  
  
## 개발 환경 이외에서 설정  
 컴파일러\(CL.exe\) 옵션을 설정할 수 있습니다.  
  
-   [명령줄에서 설정](../../build/reference/compiler-command-line-syntax.md)  
  
-   [명령 파일에서 설정](../../build/reference/cl-command-files.md)  
  
-   [CL 환경 변수에서 설정](../../build/reference/cl-environment-variables.md)  
  
 CL 환경 변수에서 지정한 옵션은 CL을 실행할 때마다 사용됩니다.  CL 환경 변수나 명령줄에서 명령 파일의 이름을 지정하면 명령줄에서 지정한 옵션이 사용됩니다.  명령줄이나 CL 환경 변수와는 달리 명령 파일을 사용하면 여러 줄로 구성된 옵션과 파일 이름을 사용할 수 있습니다.  
  
 컴파일러 옵션은 "왼쪽에서 오른쪽"으로 처리됩니다. 서로 충돌되는 경우 맨 오른쪽에 있는 옵션이 사용됩니다.  CL 환경 변수는 명령줄 이전에 처리되므로 CL과 명령줄이 충돌되는 경우 명령줄의 내용이 사용됩니다.  
  
## 추가 컴파일러 항목  
  
-   [컴파일 속도 향상](../../build/reference/fast-compilation.md)  
  
-   [CL에서의 링커 호출](../../build/reference/cl-invokes-the-linker.md)  
  
## 참고 항목  
 [C\/C\+\+ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)