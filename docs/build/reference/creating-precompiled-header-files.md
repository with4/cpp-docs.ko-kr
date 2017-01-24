---
title: "미리 컴파일된 헤더 파일 만들기 | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch 파일, 만들기"
  - "cl.exe 컴파일러, 코드 미리 컴파일"
  - "PCH 파일, 만들기"
  - "미리 컴파일된 헤더 파일, 만들기"
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 미리 컴파일된 헤더 파일 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft C 및 C\+\+ 컴파일러에서는 인라인 코드를 포함하는 C 또는 C\+\+ 코드를 미리 컴파일하기 위한 옵션을 제공합니다.  이 성능 향상 기능을 사용하면 안정적인 코드 본문을 컴파일하고, 컴파일된 상태의 코드를 파일에 저장하고, 후속 컴파일 타임에 아직 개발 단계에 있는 코드와 미리 컴파일된 코드를 결합할 수 있습니다.  안정적인 코드는 다시 컴파일하지 않아도 되므로 각 후속 컴파일의 속도가 더 빨라집니다.  
  
 이 단원에서는 다음과 같은 미리 컴파일된 헤더 문제에 대해 설명합니다.  
  
-   [소스 코드를 미리 컴파일하는 시기](../../build/reference/when-to-precompile-source-code.md)  
  
-   [코드를 미리 컴파일하기 위한 두 가지 선택 사항](../../build/reference/two-choices-for-precompiling-code.md)  
  
-   [미리 컴파일된 헤더의 일관성 규칙](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [프로젝트에 미리 컴파일된 헤더 사용](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 미리 컴파일된 헤더와 관련된 컴파일 옵션에 대한 참조 정보를 보려면 [\/Y\(미리 컴파일된 헤더\)](../../build/reference/y-precompiled-headers.md)를 참조하십시오.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)