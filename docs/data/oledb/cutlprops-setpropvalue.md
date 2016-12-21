---
title: "CUtlProps::SetPropValue | Microsoft Docs"
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
  - "SetPropValue"
  - "ATL::CUtlProps<T>::SetPropValue"
  - "ATL.CUtlProps<T>.SetPropValue"
  - "ATL.CUtlProps.SetPropValue"
  - "CUtlProps::SetPropValue"
  - "CUtlProps<T>::SetPropValue"
  - "CUtlProps.SetPropValue"
  - "CUtlProps<T>.SetPropValue"
  - "ATL::CUtlProps::SetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetPropValue 메서드"
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::SetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets a property in a property set.  
  
## 구문  
  
```  
  
      HRESULT SetPropValue(  
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
 \[in\] A pointer to a variant that contains the new property value.  
  
## 반환 값  
 `Failure` on failure and `S_OK` if successful.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)