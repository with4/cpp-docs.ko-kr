---
title: "창 프로시저 진입점 | Microsoft Docs"
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
  - "진입점, 창 프로시저"
  - "MFC, 상태 데이터 관리"
  - "상태 관리, 창 프로시저"
  - "창 프로시저 진입점"
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 창 프로시저 진입점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To protect MFC window procedures, a module static links with a special window procedure implementation.  The linkage occurs automatically when the module is linked with MFC.  This window procedure uses the `AFX_MANAGE_STATE` macro to properly set the effective module state, then it calls **AfxWndProc**, which in turn delegates to the `WindowProc` member function of the appropriate `CWnd`\-derived object.  
  
## 참고 항목  
 [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)