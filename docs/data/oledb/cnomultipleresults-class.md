---
title: "CNoMultipleResults 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CNoMultipleResults"
  - "ATL.CNoMultipleResults"
  - "ATL::CNoMultipleResults"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoMultipleResults 클래스"
ms.assetid: 343e77c4-b319-476e-b592-901ab9b2f34e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CNoMultipleResults 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Used as a template argument \(*TMultiple*\) to [CCommand](../../data/oledb/ccommand-class.md) to create an optimized command that handles a single result set.  
  
## 구문  
  
```  
class CNoMultipleResults  
```  
  
## 설명  
 If you want a command to handle multiple result sets, use [CMultipleResults](../../data/oledb/cmultipleresults-class.md) instead.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)