---
title: "종료 처리기 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예외 처리, 종료 처리기"
  - "예외, 종료"
  - "처리기"
  - "처리기, 종료"
  - "구조적 예외 처리, 종료 처리기"
  - "종료 처리기"
  - "종료 처리기, 작성"
  - "try-catch 키워드[C++], 종료 처리기"
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 종료 처리기 작성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

예외 처리기와 달리 종료 처리기는 보호된 코드 블록이 정상적으로 종료되었는지 여부와 관계없이 항상 실행됩니다.  종료 처리기의 유일한 목적은 코드 섹션의 실행 완료 방법과 관계없이 메모리, 핸들 및 파일과 같은 리소스가 제대로 닫혔는지 확인하는 것이어야 합니다.  
  
 종료 처리기는 try\-finally 문을 사용합니다.  
  
## 추가 정보  
  
-   [try\-finally 문](../cpp/try-finally-statement.md)  
  
-   [리소스 정리](../cpp/cleaning-up-resources.md)  
  
-   [예외 처리에서의 작업 타이밍](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [종료 처리기에 대한 제한](../cpp/restrictions-on-termination-handlers.md)  
  
## 참고 항목  
 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)