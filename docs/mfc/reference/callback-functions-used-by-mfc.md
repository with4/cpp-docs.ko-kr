---
title: "MFC에서 사용하는 콜백 함수 | Microsoft Docs"
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
  - "vc.mfc.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "콜백 함수"
  - "콜백 함수, MFC"
  - "함수[C++], 콜백"
  - "MFC, 콜백 함수"
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC에서 사용하는 콜백 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Three callback functions appear in the Microsoft Foundation Class Library.  A description of callback functions that are passed to [CDC::EnumObjects](../Topic/CDC::EnumObjects.md), [CDC::GrayString](../Topic/CDC::GrayString.md), and [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) follows this topic.  For the general usage of the callback functions, see the Remarks section of these member functions.  Note that all callback functions must trap MFC exceptions before returning to Windows, since exceptions cannot be thrown across callback boundaries.  For more information about exceptions, see the article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)