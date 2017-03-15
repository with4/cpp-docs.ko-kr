---
title: "프레임 창 스타일(MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FWS_ADDTOTITLE"
  - "FWS_SNAPTOBARS"
  - "FWS_PREFIXTITLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "프레임 창, 스타일"
  - "FWS_ADDTOTITLE 상수"
  - "FWS_PREFIXTITLE 상수"
  - "FWS_SNAPTOBARS 상수"
  - "스타일, windows"
ms.assetid: d21f270e-a088-4962-a2ae-8c03334b5a06
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 프레임 창 스타일(MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **FWS\_ADDTOTITLE** Specifies information to append to the end of a frame window title.  For example, "Microsoft Draw \- Drawing in Document1".  You can specify the strings displayed in the Document Template Strings tab in the Application Wizard.  If you need to turn this option off, override the `CWnd::PreCreateWindow` member function.  
  
-   **FWS\_PREFIXTITLE** Shows the document name before the application name in a frame window title.  For example, "Document \- WordPad".  You can specify the strings displayed in the Document Template Strings tab in the Application Wizard.  If you need to turn this option off, override the `CWnd::PreCreateWindow` member function.  
  
-   **FWS\_SNAPTOBARS** Controls sizing of the frame window that encloses a control bar when it is in a floating window rather than docked to a frame window.  This style sizes the window to fit the control bar.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)