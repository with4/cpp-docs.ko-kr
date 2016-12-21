---
title: "소스 코드를 미리 컴파일하는 시기 | Microsoft Docs"
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
  - "미리 컴파일된 헤더 파일, 미리 컴파일하는 시기"
  - "소스 코드, 미리 컴파일"
ms.assetid: eb8ba193-fd87-40d3-9545-c75deabe37cb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 소스 코드를 미리 컴파일하는 시기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 코드는 개발 과정에서 컴파일 타임을 줄여 주기 때문에 특히 다음과 같은 경우에 유용합니다.  
  
-   자주 바뀌지 않고 크기가 큰 코드 본문을 항상 사용합니다.  
  
-   프로그램이 여러 개의 모듈로 구성되어 있으며, 모든 모듈이 포함 파일의 표준 집합 및 동일한 컴파일 옵션을 사용합니다.  이 경우 모든 포함 파일을 미리 컴파일해서 하나의 미리 컴파일된 헤더로 만들 수 있습니다.  
  
 최초의 컴파일\(미리 컴파일된 헤더 파일을 만드는 단계\)에는 후속 컴파일보다 시간이 약간 더 걸립니다.  하지만 후속 컴파일은 미리 컴파일된 코드를 포함하므로 더 빠르게 진행됩니다.  
  
 C 프로그램과 C\+\+ 프로그램을 모두 미리 컴파일할 수 있습니다.  C\+\+ 프로그래밍에서는 클래스 인터페이스 정보를 몇 개의 헤더 파일에 분리시키는 것이 일반적인 관행입니다.  이 헤더 파일들은 나중에 해당 클래스를 사용하는 프로그램에 포함될 수 있습니다.  이 헤더를 미리 컴파일하면 프로그램이 컴파일을 수행하는 데 걸리는 시간을 줄일 수 있습니다.  
  
> [!NOTE]
>  미리 컴파일된 헤더\(.pch\) 파일은 각 소스 파일에 대해 하나씩만 사용할 수 있지만 프로젝트에서는 여러 개의 .pch 파일을 사용할 수 있습니다.  
  
## 참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)