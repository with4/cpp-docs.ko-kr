---
title: "ML Nonfatal Error A2050 | Microsoft Docs"
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
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**실제 또는 BCD 번호가 허용 되지 않습니다**  
  
 \(실제\) 부동 소수점 숫자 또는 바이너리 coded 10 진수 \(BCD\) 상수가 아닌 다른 사용 된 데이터 이니셜라이저로 합니다.  
  
 다음 중 하나가 발생 했습니다.  
  
-   실수 또는 BCD 식에 사용 되었습니다.  
  
-   실수 이외의 지시문을 초기화 하는 데 사용 된  [DWORD](../../assembler/masm/dword.md),  [QWORD](../../assembler/masm/qword.md), 또는  [TBYTE](../../assembler/masm/tbyte.md).  
  
-   BCD는 지시문 이외의 초기화에 사용 된 `TBYTE`.  
  
## 참고 항목  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)