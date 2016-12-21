---
title: "CNoRowset 클래스 | Microsoft Docs"
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
  - "ATL.CNoRowset"
  - "ATL::CNoRowset<TAccessor>"
  - "CNoRowset"
  - "ATL.CNoRowset<TAccessor>"
  - "ATL::CNoRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoRowset 클래스"
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CNoRowset 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Can be used as a template argument \(`TRowset`\) for [CCommand](../../data/oledb/ccommand-class.md) or [CTable](../../data/oledb/ctable-class.md).  
  
## 구문  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### 매개 변수  
 `TAccessor`  
 An accessor class.  기본값은 `CAccessorBase`입니다.  
  
## 설명  
 Use `CNoRowset` as a template argument if the command does not return a rowset.  
  
 `CNoRowset` implements the following stub methods, each of which correspond to other accessor class methods:  
  
-   **BindFinished** \- Indicates when binding is complete \(returns `S_OK`\).  
  
-   **Close** \- Releases rows and the current IRowset interface.  
  
-   `GetIID` \- Retrieves the interface ID of a connection point.  
  
-   **GetInterface** \- Retrieves an interface.  
  
-   `GetInterfacePtr` \- Retrieves an encapsulated interface pointer.  
  
-   **SetAccessor** \- Sets a pointer to the accessor.  
  
-   **SetupOptionalRowsetInterfaces** \- Sets up optional interfaces for the rowset.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)