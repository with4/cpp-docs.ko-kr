---
title: "표준 명령 | Microsoft Docs"
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
  - "명령 ID, 표준 명령"
  - "명령[C++], 표준"
  - "편집 메뉴 표준 명령"
  - "파일 메뉴"
  - "도움말, 메뉴"
  - "식별자[C++], 명령 ID"
  - "OLE 명령"
  - "프로그래머 정의 ID[C++]"
  - "표준 명령 ID"
  - "표준 명령"
  - "보기 메뉴 명령"
  - "창 메뉴 명령"
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 표준 명령
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The framework defines many standard command messages.  The IDs for these commands typically take the form:  
  
 **ID\_** *Source*\_*Item*  
  
 where *Source* is usually a menu name and *Item* is a menu item.  For example, the command ID for the New command on the File menu is `ID_FILE_NEW`.  Standard command IDs are shown in bold type in the documentation.  Programmer\-defined IDs are shown in a font that is different from the surrounding text.  
  
 The following is a list of some of the most important commands supported:  
  
 *File Menu Commands*  
 New, Open, Close, Save, Save As, Page Setup, Print Setup, Print, Print Preview, Exit, and most\-recently\-used files.  
  
 *Edit Menu Commands*  
 Clear, Clear All, Copy, Cut, Find, Paste, Repeat, Replace, Select All, Undo, and Redo.  
  
 *보기 메뉴 명령*  
 Toolbar and Status Bar.  
  
 *창 메뉴 명령*  
 New, Arrange, Cascade, Tile Horizontal, Tile Vertical, and Split.  
  
 *도움말 메뉴 명령*  
 Index, Using Help, and About.  
  
 *OLE Commands \(Edit Menu\)*  
 Insert New Object, Edit Links, Paste Link, Paste Special, and *typename* Object \(verb commands\).  
  
 The framework provides varying levels of support for these commands.  Some commands are supported only as defined command IDs, while others are supported with thorough implementations.  For example, the framework implements the Open command on the File menu by creating a new document object, displaying an Open dialog box, and opening and reading the file.  In contrast, you must implement commands on the Edit menu yourself, since commands like **ID\_EDIT\_COPY** depend on the nature of the data you are copying.  
  
 For more information about the commands supported and the level of implementation provided, see [Technical Note 22](../mfc/tn022-standard-commands-implementation.md).  The standard commands are defined in the file AFXRES.H.  
  
## 참고 항목  
 [사용자 인터페이스 개체 및 명령 ID](../mfc/user-interface-objects-and-command-ids.md)