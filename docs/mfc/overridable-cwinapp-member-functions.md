---
title: "재정의 가능 CWinApp 멤버 함수 | Microsoft Docs"
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
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 클래스"
  - "CWinApp 클래스, 재정의 가능"
  - "재정의, CWinApp 재정의 가능 함수"
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 재정의 가능 CWinApp 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinApp](../mfc/reference/cwinapp-class.md) 는 다양한 재정의 가능한 키 멤버 함수를 제공합니다. \(`CWinApp` 는 `CWinApp` 가 파생한 [CWinThread](../mfc/reference/cwinthread-class.md) 에서 이러한 함수를 재정의 합니다.  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [실행](../mfc/run-member-function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [OnIdle](../mfc/onidle-member-function.md)  
  
 재정의 해야 하는 `CWinApp` 멤버 함수는 `InitInstance` 입니다.  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)