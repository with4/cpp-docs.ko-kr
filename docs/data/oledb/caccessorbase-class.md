---
title: "CAccessorBase 클래스 | Microsoft Docs"
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
  - "CAccessorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorBase 클래스"
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

All accessors in the OLE DB Templates derive from this class.  `CAccessorBase` allows one rowset to manage multiple accessors.  It also provides binding for both parameters and output columns.  
  
## 구문  
  
```  
// Replace with syntax  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[닫기](../../data/oledb/caccessorbase-close.md)|Closes the accessors.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|Retrieves the accessor handle.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|Retrieves the number of accessors created by the class.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|Tests whether the specified accessor is an autoaccessor.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|Releases the accessors.|  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)