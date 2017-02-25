---
title: "abort 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort 함수"
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# abort 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 포함 파일 STDLIB.H에서 선언된 **abort** 함수는 C\+\+ 프로그램을 종료합니다.  **exit**와 **abort**의 차이는 **exit**에서는 C\+\+ 런타임 종료 처리 과정이 발생하지만\(전역 개체 소멸자 호출\) **abort**에서는 프로그램이 즉시 종료된다는 점입니다.  자세한 내용은 런타임 라이브러리 참조에서 [abort](../c-runtime-library/reference/abort.md)를 참조하십시오.  
  
## 참고 항목  
 [프로그램 종료](../cpp/program-termination.md)