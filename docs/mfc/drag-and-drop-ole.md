---
title: "끌어서 놓기(OLE) | Microsoft Docs"
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
  - "끌어서 놓기[C++]"
  - "끌어서 놓기[C++], OLE 끌어서 놓기 정보"
  - "파일 관리자 끌어서 놓기 지원"
  - "OLE 응용 프로그램, 끌어서 놓기"
  - "OLE 끌어서 놓기"
  - "OLE 서버 응용 프로그램, 끌어서 놓기"
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 끌어서 놓기(OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The drag\-and\-drop feature of OLE is primarily a shortcut for copying and pasting data.  When you use the Clipboard to copy or paste data, a number of steps are required.  You select the data, click **Cut** or **Copy** from the **Edit** menu, move to the destination file, window or application, place the cursor in the desired location, and click **Paste** from the **Edit** menu.  
  
 OLE drag and drop is different from the File Manager drag\-and\-drop mechanism, which can only handle filenames and is designed specifically to pass filenames to applications.  OLE drag and drop is much more general.  It allows you to drag and drop any data that could also be placed on the Clipboard.  
  
 When you use OLE drag and drop, you remove two steps from the process.  You select the data from the source window \(the "drop source"\), drag it to the desired destination \(the "drop target"\), and drop it by releasing the mouse button.  The operation eliminates the need for menus and is quicker than the copy\/paste sequence.  The only requirement is that both the drop source and drop target must be open and at least partially visible on the screen.  
  
 Using OLE drag and drop, data can be transferred from one location to another within a document, between different documents, or between applications.  It can be implemented in either a container or a server application, and any application can be a drop source, a drop target, or both.  If an application has both drop\-source and drop\-target support implemented, drag and drop is enabled between child windows, or within one window.  This feature can make your application much easier to use.  
  
 If you only want to use the drag\-and\-drop capabilities of OLE, see [Drag and Drop: Customizing](../mfc/drag-and-drop-customizing.md).  You can use the techniques explained in that article to make non\-OLE applications drop sources.  The article [Drag and Drop: Implementing a Drop Target](../mfc/drag-and-drop-implementing-a-drop-target.md) describes how to implement drop\-target support for both OLE and non\-OLE applications.  It will also be helpful to examine the MFC OLE samples [OCLIENT](../top/visual-cpp-samples.md) and [HIERSVR](../top/visual-cpp-samples.md).  
  
 If you have not read the [Data Objects and Data Sources \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) family of articles, you may want to do so now.  These articles explain the fundamentals of data transfer, and how to implement it in your applications.  
  
 For more information about drag and drop, see:  
  
-   [Drag and Drop: Implementing a Drop Source](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Drag and Drop: Implementing a Drop Target](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Drag and Drop: Customizing](../mfc/drag-and-drop-customizing.md)  
  
## 참고 항목  
 [OLE](../mfc/ole-in-mfc.md)   
 [데이터 개체 및 데이터 소스\(OLE\)](../mfc/data-objects-and-data-sources-ole.md)