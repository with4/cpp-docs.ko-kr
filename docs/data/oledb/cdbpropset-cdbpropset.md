---
title: "CDBPropSet::CDBPropSet | Microsoft Docs"
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
  - "CDBPropSet.CDBPropSet"
  - "CDBPropSet::CDBPropSet"
  - "ATL::CDBPropSet::CDBPropSet"
  - "ATL.CDBPropSet.CDBPropSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropSet 클래스, 생성자"
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::CDBPropSet
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성자입니다.  **rgProperties**, **cProperties**, 및  **guidPropertySet** 필드는  [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조를 초기화합니다.  
  
## 구문  
  
```  
  
      CDBPropSet(  
   const GUID& guid   
);  
CDBPropSet(   
   const CDBPropSet& propset    
);  
CDBPropSet( );  
```  
  
#### 매개 변수  
 `guid`  
 \[in\] GUID를 초기화 하는 데는  **guidPropertySet** 필드입니다.  
  
 *propset*  
 \[in\] 다른  `CDBPropSet`  복사 생성에 대 한 개체입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDBPropSet 클래스](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::SetGUID](../../data/oledb/cdbpropset-setguid.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)