---
title: "PAINTSTRUCT 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PAINTSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PAINTSTRUCT 구조체"
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# PAINTSTRUCT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `PAINTSTRUCT` structure contains information that can be used to paint the client area of a window.  
  
## 구문  
  
```  
  
      typedef struct tagPAINTSTRUCT {  
   HDC hdc;  
   BOOL fErase;  
   RECT rcPaint;  
   BOOL fRestore;  
   BOOL fIncUpdate;  
   BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### 매개 변수  
 *hdc*  
 Identifies the display context to be used for painting.  
  
 *fErase*  
 Specifies whether the background needs to be redrawn.  It is not 0 if the application should redraw the background.  The application is responsible for drawing the background if a Windows window\-class is created without a background brush \(see the description of the **hbrBackground** member of the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 *rcPaint*  
 Specifies the upper left and lower right corners of the rectangle in which the painting is requested.  
  
 *fRestore*  
 Reserved member.  It is used internally by Windows.  
  
 *fIncUpdate*  
 Reserved member.  It is used internally by Windows.  
  
 *rgbReserved\[16\]*  
 Reserved member.  A reserved block of memory used internally by Windows.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)