---
title: "매크로 정의의 우선 순위 | Microsoft Docs"
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
helpviewer_keywords: 
  - "매크로, 우선 순위"
  - "NMAKE 프로그램, 매크로 정의의 우선 순위"
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 매크로 정의의 우선 순위
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

매크로에 여러 개의 정의가 포함된 경우 NMAKE는 우선 순위가 가장 높은 정의를 사용합니다.  다음 목록은 우선 순위를 최상위에서 최하위 순으로 나타냅니다.  
  
1.  명령줄에 정의된 매크로  
  
2.  메이크파일 또는 포함 파일에 정의된 매크로  
  
3.  상속된 환경 변수 매크로  
  
4.  Tools.ini 파일에 정의된 매크로  
  
5.  [CC](../build/command-macros-and-options-macros.md) 및 [AS](../build/command-macros-and-options-macros.md) 등의 미리 정의된 매크로  
  
 환경 변수로부터 매크로를 상속하여 같은 이름의 메이크파일 매크로를 재정의하려면 \/E를 사용합니다.  명령줄을 재정의하려면 **\!UNDEF**를 사용합니다.  
  
## 참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)