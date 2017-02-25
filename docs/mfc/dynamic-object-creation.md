---
title: "동적 개체 만들기 | Microsoft Docs"
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
  - "CObject 클래스, 동적 개체 만들기"
  - "동적 개체 만들기"
  - "개체 만들기, 런타임에 동적으로"
  - "개체[C++], 런타임에 동적으로 만들기"
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 동적 개체 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains how to create an object dynamically at run time.  The procedure uses run\-time class information, as discussed in the article [Accessing Run\-Time Class Information](../mfc/accessing-run-time-class-information.md).  
  
#### To dynamically create an object given its run\-time class  
  
1.  Use the following code to dynamically create an object by using the `CreateObject` function of the `CRuntimeClass`.  Note that on failure, `CreateObject` returns **NULL** instead of raising an exception:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/CPP/dynamic-object-creation_1.cpp)]  
  
## 참고 항목  
 [CObject 사용](../mfc/using-cobject.md)