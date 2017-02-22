---
title: "프레임 창에서 파일 끌어서 놓기 | Microsoft Docs"
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
  - "끌어서 놓기[C++], 파일 관리자"
  - "끌어서 놓기[C++], 파일"
  - "끌어서 놓기[C++], Windows 탐색기"
  - "파일 관리자 끌어서 놓기 지원"
  - "파일[C++], 끌어서 놓기"
  - "프레임 창[C++], 파일 끌어서 놓기"
  - "Windows 탐색기[C++]"
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 프레임 창에서 파일 끌어서 놓기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The frame window manages a relationship with File Explorer or File Manager.  
  
 By adding a few initializing calls in your override of the `CWinApp` member function `InitInstance`, as described in [CWinApp: The Application Class](../mfc/cwinapp-the-application-class.md), you can have your frame window indirectly open files dragged from File Explorer or File Manager and dropped in the frame window.  See [File Manager Drag and Drop](../mfc/special-cwinapp-services.md).  
  
## 참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)