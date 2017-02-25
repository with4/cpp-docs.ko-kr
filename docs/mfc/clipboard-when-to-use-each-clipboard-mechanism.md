---
title: "클립보드: 각 클립보드 메커니즘을 사용하는 경우 | Microsoft Docs"
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
  - "응용 프로그램[OLE], 클립보드"
  - "클립보드[C++], 형식"
  - "클립보드[C++], 메커니즘"
  - "서식[C++], OLE의 클립보드"
  - "OLE 클립보드, 형식"
  - "OLE 클립보드, 지침"
ms.assetid: fd071996-ef8c-488b-81bd-89057095a201
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 클립보드: 각 클립보드 메커니즘을 사용하는 경우
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Follow these guidelines in using the Clipboard:  
  
-   Use the OLE Clipboard mechanism now to enable new capabilities in the future.  While the standard Clipboard API will be maintained, the OLE mechanism is the future of data transfer.  
  
-   Use the OLE Clipboard mechanism if you are writing an OLE application or you want any of the OLE features, such as drag and drop.  
  
-   Use the OLE Clipboard mechanism if you are providing OLE formats.  
  
## 수행할 작업  
  
-   [Use the OLE Clipboard mechanism](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Use the Windows Clipboard mechanism](../mfc/clipboard-using-the-windows-clipboard.md)  
  
## 참고 항목  
 [클립보드](../mfc/clipboard.md)