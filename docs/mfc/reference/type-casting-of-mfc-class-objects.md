---
title: "MFC 클래스 개체의 형식 캐스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "형식 캐스팅"
  - "매크로, 포인터 캐스팅"
  - "매크로, 형식 캐스팅"
  - "포인터, 형식 캐스팅"
  - "형식 캐스팅"
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# MFC 클래스 개체의 형식 캐스팅
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Type casting macros provide a way to cast a given pointer to a pointer that points to an object of specific class, with or without checking that the cast is legal.  
  
 The following table lists the MFC type casting macros.  
  
### Macros That Cast Pointers to MFC Class Objects  
  
|||  
|-|-|  
|[DYNAMIC\_DOWNCAST](../Topic/DYNAMIC_DOWNCAST.md)|Casts a pointer to a pointer to a class object while checking to see if the cast is legal.|  
|[STATIC\_DOWNCAST](../Topic/STATIC_DOWNCAST.md)|Casts a pointer to an object from one class to a pointer of a related type.  In a debug build, causes an **ASSERT** if the object is not a "kind of" the target type.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)