---
title: "CColumnAccessor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CColumnAccessor"
  - "ATL::CColumnAccessor"
  - "ATL.CColumnAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnAccessor 클래스"
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CColumnAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generates injected consumer code.  
  
## 구문  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## 설명  
 In the injected code, every column is bound as a separate accessor.  You should be aware that this class is used in the injected code \(for example, you might encounter it when debugging\), but you typically never have to use it or its methods directly.  
  
 `CColumnAccessor` implements the following stub methods, each of which correspond in functionality to other accessor class methods:  
  
-   `CColumnAccessor` The constructor; instantiates and initializes the `CColumnAccessor` object.  
  
-   `CreateAccessor` Allocates memory for the column binding structures and initializes the column data members.  
  
-   **BindColumns** Binds columns to accessors.  
  
-   **SetParameterBuffer** Allocates buffers for parameters.  
  
-   `AddParameter` Adds a parameter entry to the parameter entry structures.  
  
-   **HasOutputColumns** Determines whether the accessor has output columns  
  
-   **HasParameters** Determines whether the accessor has parameters.  
  
-   `BindParameters` Binds the created parameters to columns.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)