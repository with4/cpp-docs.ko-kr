---
title: "표준 명령 라우팅 재정의 | Microsoft Docs"
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
  - "명령 처리, 명령 라우팅"
  - "명령 라우팅, 재정의"
  - "MFC, 명령 라우팅"
  - "재정의, 표준 명령 라우팅"
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 표준 명령 라우팅 재정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In rare cases when you must implement some variation of the standard framework routing, you can override it.  The idea is to change the routing in one or more classes by overriding `OnCmdMsg` in those classes.  Do so:  
  
-   In the class that breaks the order to pass to a nondefault object.  
  
-   In the new nondefault object or in command targets it might in turn pass commands to.  
  
 If you insert some new object into the routing, its class must be a command\-target class.  In your overriding versions of `OnCmdMsg`, be sure to call the version that you're overriding.  See the [OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md) member function of class `CCmdTarget` in the *MFC Reference* and the versions in such classes as `CView` and **CDocument** in the supplied source code for examples.  
  
## 참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)