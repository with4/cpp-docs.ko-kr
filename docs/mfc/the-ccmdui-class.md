---
title: "CCmdUI 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdUI 클래스, 메뉴 업데이트"
  - "도구 모음[C++], 업데이트"
  - "업데이트 처리기"
  - "사용자 인터페이스 개체 업데이트"
  - "사용자 인터페이스 개체, 업데이트"
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CCmdUI 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When it routes an update command to its handler, the framework passes the handler a pointer to a `CCmdUI` object \(or to an object of a `CCmdUI`\-derived class\).  This object represents the menu item or toolbar button or other user\-interface object that generated the command.  The update handler calls member functions of the `CCmdUI` structure through the pointer to update the user\-interface object.  For example, here is an update handler for the Clear All menu item:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/CPP/the-ccmdui-class_1.cpp)]  
  
 This handler calls the **Enable** member function of an object with access to the menu item.  **Enable** makes the item available for use.  
  
## 참고 항목  
 [방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)