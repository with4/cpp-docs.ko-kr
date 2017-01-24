---
title: "파일 이름 부분 구문 | Microsoft Docs"
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
  - "NMAKE의 파일 이름 부분 구문"
  - "NMAKE 프로그램, 구문"
  - "구문, 파일 이름 부분"
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 파일 이름 부분 구문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

명령의 파일 이름 부분 구문은 첫 번째 종속 파일 이름\(변환된 종속 파일일 수도 있음\)의 구성 요소를 나타냅니다.  파일 이름 구성 요소는 파일의 드라이브, 경로, 기본 이름 및 지정한 대로의 확장명입니다\(디스크에서 사용하는 확장명이 아님\).  전체 파일 이름을 나타내려면 **%s**를 사용합니다.  파일 이름의 일부를 나타내려면 **%&#124;**\[*parts*\]**F**를 사용합니다. 이 때 백분율 기호 다음에는 세로 막대 문자가 오며 *parts*에는 다음 문자를 임의의 순서로 0개 이상 사용할 수 있습니다.  
  
|레터|설명|  
|--------|--------|  
|문자 없음|전체 이름\(**%s**와 같음\)|  
|**d**|드라이브|  
|**p**|경로|  
|**f**|기본 파일 이름|  
|**e**|파일 확장명|  
  
 예를 들어, 파일 이름이 c:\\prog.exe인 경우 각 구문이 나타내는 파일 이름 부분은 다음과 같습니다.  
  
-   %s는 c:\\prog.exe를 나타냅니다.  
  
-   %&#124;F는 c:\\prog.exe를 나타냅니다.  
  
-   %&#124;dF는 c를 나타냅니다.  
  
-   %&#124;pF는 c:\\를 나타냅니다.  
  
-   %&#124;fF는 prog를 나타냅니다.  
  
-   %&#124;eF는 exe를 나타냅니다.  
  
## 참고 항목  
 [메이크파일의 명령](../build/commands-in-a-makefile.md)