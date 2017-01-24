---
title: "대화 상자 소멸시키기 | Microsoft Docs"
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
  - "소멸, 대화 상자"
  - "대화 상자, 제거"
  - "대화 상자, 소멸"
  - "대화 상자, 제거"
  - "MFC 대화 상자, 소멸"
  - "모달 대화 상자, 소멸"
  - "모덜리스 대화 상자, 소멸"
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자 소멸시키기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Modal dialog boxes are normally created on the stack frame and destroyed when the function that created them ends.  The dialog object's destructor is called when the object goes out of scope.  
  
 Modeless dialog boxes are normally created and owned by a parent view or frame window — the application's main frame window or a document frame window.  The default [OnClose](../Topic/CWnd::OnClose.md) handler calls [DestroyWindow](../Topic/CWnd::DestroyWindow.md), which destroys the dialog\-box window.  If the dialog box stands alone, with no pointers to it or other special ownership semantics, you should override [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md) to destroy the C\+\+ dialog object.  You should also override [OnCancel](../Topic/CDialog::OnCancel.md) and call `DestroyWindow` from within it.  If not, the owner of the dialog box should destroy the C\+\+ object when it is no longer necessary.  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)