---
title: "CString Exception Cleanup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString objects, 예외"
  - "예외 처리, cleanup code"
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CString Exception Cleanup
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이전 버전의 MFC 정리 하는 것이 중요 한  [CString](../atl-mfc-shared/reference/cstringt-class.md) 개체를 사용 합니다.  MFC 버전 3.0 이상에서 명시적 정리가 더 이상 필요합니다.  
  
 이제 MFC를 사용 하는 메커니즘을 처리 하는 C\+\+ 예외에서 예외가 발생 한 후 정리에 대 한 걱정할 필요가 없습니다.  "예외가 발생 한 후는 방법에 대 한 설명은 C\+\+의 스택 해제"를 참조 하십시오  [try, catch 및 throw 문](../cpp/try-throw-and-catch-statements-cpp.md).  MFC를 사용 하는 경우에  **시도**\/**CATCH** 매크로 대신 C\+\+ 키워드  **시도** 및  **catch**, C\+\+ 예외 메커니즘 아래 MFC를 사용 하 여, 계속 하도록 명시적으로 정리할 필요가 없습니다.  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)   
 [예외 처리](../mfc/exception-handling-in-mfc.md)