---
title: "CUtlProps::GetPropValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps::GetPropValue"
  - "CUtlProps.GetPropValue"
  - "GetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetPropValue 메서드"
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::GetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gets a property from a property set.  
  
## 구문  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### 매개 변수  
 `pguidPropSet`  
 \[in\] The GUID for the PropSet.  
  
 `dwPropId`  
 \[in\] The property index.  
  
 `pvValue`  
 \[out\] A pointer to a variant that contains the new property value.  
  
## 반환 값  
 `Failure` on failure and `S_OK` if successful.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)