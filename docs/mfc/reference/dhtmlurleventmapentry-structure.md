---
title: "DHtmlUrlEventMapEntry 구조체 | Microsoft Docs"
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
  - "DHtmlUrlEventMapEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHtmlUrlEventMapEntry 구조체"
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DHtmlUrlEventMapEntry 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `DHtmlUrlEventMapEntry` structure provides multi\-URL event map support.  
  
## 구문  
  
```  
  
      struct DHtmlUrlEventMapEntry  
{  
   LPCTSTR szUrl;  
   const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### 매개 변수  
 `szUrl`  
 URL입니다.  
  
 *pEventMap*  
 The event map associated with the URL.  
  
## 요구 사항  
 **Header:** afxdhtml.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)