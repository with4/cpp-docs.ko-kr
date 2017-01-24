---
title: "CDC::SetAbortProc에 대한 콜백 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::SetAbortProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "콜백 함수, CDC::SetAbortProc"
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDC::SetAbortProc에 대한 콜백 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The name *AbortFunc* is a placeholder for the application\-supplied function name.  
  
## 구문  
  
```  
  
      BOOL CALLBACK EXPORT AbortFunc(   
   HDC hPr,   
   int code    
);  
```  
  
#### 매개 변수  
 *hPr*  
 Identifies the device context.  
  
 `code`  
 Specifies whether an error has occurred.  It is 0 if no error has occurred.  It is **SP\_OUTOFDISK** if the Print Manager is currently out of disk space and more disk space will become available if the application waits.  If `code` is **SP\_OUTOFDISK**, the application does not have to abort the print job.  If it does not, it must yield to the Print Manager by calling the **PeekMessage** or **GetMessage** Windows function.  
  
## 반환 값  
 The return value of the abort\-handler function is nonzero if the print job is to continue, and 0 if it is canceled.  
  
## 설명  
 The actual name must be exported as described in the Remarks section of [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md).  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)