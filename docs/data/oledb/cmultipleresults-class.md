---
title: "CMultipleResults 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CMultipleResults"
  - "ATL::CMultipleResults"
  - "CMultipleResults"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultipleResults 클래스"
ms.assetid: 6ce5bbb9-b551-483c-988a-e6aee9135a19
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CMultipleResults 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

If you want a command to handle multiple result sets, use `CMultipleResults` for the `CCommand` template argument *TMultiple*.  
  
## 구문  
  
```  
class CMultipleResults  
```  
  
## 설명  
 To handle multiple result sets, [CCommand](../../data/oledb/ccommand-class.md) must inherit from this class.  
  
## 요구 사항  
 **Header:** atldbcli  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)