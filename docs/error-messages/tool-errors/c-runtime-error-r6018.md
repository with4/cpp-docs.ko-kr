---
title: "C 런타임 오류 R6018 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6018"
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C 런타임 오류 R6018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예기치 못한 힙 오류입니다.  
  
 메모리 관리 작업을 수행하는 동안 예기치 못한 오류가 발생했습니다.  
  
 일반적으로 이 오류는 프로그램에서 런타임 힙 데이터를 부주의하게 변경할 때 발생합니다.  또한 런타임 코드나 운영 체제 코드의 내부 오류 때문에 발생할 수 있습니다.  
  
 컴파일러에서 `_heapchk` 및 `_heapwalk`가 들어 있는 라이브러리를 제공할 경우 이들 함수를 사용하여 오류를 진단할 수 있습니다.