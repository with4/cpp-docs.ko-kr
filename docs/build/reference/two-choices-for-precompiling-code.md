---
title: "코드를 미리 컴파일하기 위한 두 가지 선택 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - ".pch 파일"
  - ".pch 파일, 미리 컴파일 옵션"
  - "자동으로 미리 컴파일"
  - "코드, 미리 컴파일"
  - "소스 코드 컴파일, 미리 컴파일"
  - "PCH 파일"
  - "PCH 파일, 미리 컴파일 옵션"
  - "미리 컴파일된 헤더 파일"
  - "미리 컴파일된 헤더 파일, 미리 컴파일 옵션"
  - "코드 미리 컴파일"
ms.assetid: f50ac76f-e2a2-462d-bda5-0e2ab7cccdeb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 코드를 미리 컴파일하기 위한 두 가지 선택 사항
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+를 사용하는 경우에는 모든 C 또는 C\+\+ 코드를 미리 컴파일할 수 있으며 헤더 파일만 미리 컴파일하도록 제한되지 않습니다.  
  
 코드를 미리 컴파일하려면 계획이 필요하지만 단순한 헤더 파일 이외의 소스 코드를 미리 컴파일하는 경우 컴파일 속도가 훨씬 더 빨라집니다.  
  
 여러 개의 소스 파일이 헤더 파일의 공용 집합을 사용하지만 이 헤더 파일들을 동일한 순서로 포함하지는 않는 경우나 미리 컴파일하는 작업에 소스 코드를 포함시키려는 경우에 코드를 미리 컴파일합니다.  
  
 미리 컴파일된 헤더 옵션은 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)와 [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)입니다.  **\/Yc**는 미리 컴파일된 헤더를 만드는 데 사용합니다.  **\/Yc** 옵션을 선택적 pragma인 `hdrstop`과 함께 사용하면 헤더 파일과 소스 코드를 모두 미리 컴파일할 수 있습니다.  기존 컴파일 작업에서 만들어진 기존의 미리 컴파일된 헤더를 사용하려면 **\/Yu** 옵션을 선택합니다.  **\/Fp**를 **\/Yc** 및 **\/Yu** 옵션과 함께 사용하여 미리 컴파일된 헤더에 대한 다른 이름을 지정할 수도 있습니다.  
  
 **\/Yu** 및 **\/Yc**에 대한 컴파일러 옵션 참조 항목에서는 개발 환경에서 이 기능을 사용하는 방법에 대해 설명합니다.  
  
## 추가 정보  
  
-   [소스 코드를 미리 컴파일하는 시기](../../build/reference/when-to-precompile-source-code.md)  
  
-   [미리 컴파일된 헤더의 일관성 규칙](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [프로젝트에 미리 컴파일된 헤더 사용](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 미리 컴파일된 헤더의 사용에 대한 자세한 예제를 보려면 MFC 라이브러리와 함께 제공되는 샘플 프로그램을 빌드하는 데 사용되는 메이크파일을 참조하십시오.  
  
## 참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)