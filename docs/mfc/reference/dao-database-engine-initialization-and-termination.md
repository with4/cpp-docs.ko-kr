---
title: "DAO 데이터베이스 엔진 초기화 및 종료 | Microsoft Docs"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO(Data Access Objects), 초기화"
  - "DAO(Data Access Objects), 종료"
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO 데이터베이스 엔진 초기화 및 종료
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

When using MFC DAO objects, the DAO database engine must first be initialized and then terminated before your application or DLL quits.  Two functions, `AfxDaoInit` and `AfxDaoTerm`, perform these tasks.  
  
### DAO Database Engine Initialization and Termination  
  
|||  
|-|-|  
|[AfxDaoInit](../Topic/AfxDaoInit.md)|Initializes the DAO database engine.|  
|[AfxDaoTerm](../Topic/AfxDaoTerm.md)|Terminates the DAO database engine.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)