---
title: "C 런타임 오류 R6008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6008"
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C 런타임 오류 R6008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수에 대한 공간이 부족합니다.  
  
 프로그램을 로드하는 데 필요한 메모리는 충분하지만 **argv** 배열을 만들기 위한 메모리가 부족합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  프로그램이 사용할 수 있는 메모리 양을 늘입니다.  
  
2.  명령줄 인수의 개수와 크기를 줄입니다.  
  
3.  필요 없는 변수를 제거하여 환경 크기를 줄입니다.