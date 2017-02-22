---
title: "클립보드: Windows 클립보드 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클립보드[C++], 명령"
  - "클립보드[C++], Windows 클립보드 API"
  - "클립보드 명령"
  - "클립보드 명령, 구현"
  - "명령[C++], 편집 구현"
  - "잘라내기/복사 및 붙여넣기 명령 처리기 함수"
  - "처리기 함수, 잘라내기/복사 및 붙여넣기 명령"
  - "Windows 클립보드[C++]"
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 클립보드: Windows 클립보드 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This topic describes how to use the standard Windows Clipboard API within your MFC application.  
  
 Most applications for Windows support cutting or copying data to the Windows Clipboard and pasting data from the Clipboard.  The Clipboard data formats vary among applications.  The framework supports only a limited number of Clipboard formats for a limited number of classes.  You will normally implement the Clipboard\-related commands — Cut, Copy, and Paste — on the Edit menu for your view.  The class library defines the command IDs for these commands: **ID\_EDIT\_CUT**, **ID\_EDIT\_COPY**, and **ID\_EDIT\_PASTE**.  Their message\-line prompts are also defined.  
  
 [Messages and Commands in the Framework](../mfc/messages-and-commands-in-the-framework.md) explains how to handle menu commands in your application by mapping the menu command to a handler function.  As long as your application does not define handler functions for the Clipboard commands on the Edit menu, they remain disabled.  To write handler functions for the Cut and Copy commands, implement selection in your application.  To write a handler function for the Paste command, query the Clipboard to see whether it contains data in a format your application can accept.  For example, to enable the Copy command, you might write a handler something like the following:  
  
 [!code-cpp[NVC_MFCListView#2](../mfc/codesnippet/CPP/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 The Cut, Copy, and Paste commands are only meaningful in certain contexts.  The Cut and Copy commands should be enabled only when something is selected, and the Paste command only when something is in the Clipboard.  You can provide this behavior by defining update handler functions that enable or disable these commands depending on the context.  For more information, see [How to Update User\-Interface Objects](../mfc/how-to-update-user-interface-objects.md).  
  
 The Microsoft Foundation Class Library does provide Clipboard support for text editing with the `CEdit` and `CEditView` classes.  The OLE classes also simplify implementing Clipboard operations that involve OLE items.  For more information on the OLE classes, see [Clipboard: Using the OLE Clipboard Mechanism](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).  
  
 Implementing other Edit menu commands, such as Undo \(**ID\_EDIT\_UNDO**\) and Redo \(**ID\_EDIT\_REDO**\), is also left to you.  If your application does not support these commands, you can easily delete them from your resource file using the Visual C\+\+ resource editors.  
  
## 추가 정보  
  
-   [Copying and pasting data](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Using the OLE Clipboard mechanism](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## 참고 항목  
 [클립보드](../mfc/clipboard.md)