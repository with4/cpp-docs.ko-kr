---
title: "CDBPropSet::AddProperty | Microsoft Docs"
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
  - "CDBPropSet::AddProperty"
  - "CDBPropSet.AddProperty"
  - "AddProperty"
  - "ATL::CDBPropSet::AddProperty"
  - "ATL.CDBPropSet.AddProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty 메서드"
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::AddProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Adds a property to the property set.  
  
## 구문  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### 매개 변수  
 *dwPropertyID*  
 \[in\] The ID of the property to be added.  Used to initialize the **dwPropertyID** of the `DBPROP` structure added to the property set.  
  
 `var`  
 \[in\] A variant used to initialize the property value for the `DBPROP` structure added to the property set.  
  
 `szValue`  
 \[in\] A string used to initialize the property value for the `DBPROP` structure added to the property set.  
  
 `bValue`  
 \[in\] A **BYTE** or boolean value used to initialize the property value for the `DBPROP` structure added to the property set.  
  
 `nValue`  
 \[in\] An integer value used to initialize the property value for the `DBPROP` structure added to the property set.  
  
 *fltValue*  
 \[in\] A floating\-point value used to initialize the property value for the `DBPROP` structure added to the property set.  
  
 `dblValue`  
 \[in\] A double\-precision floating\-point value used to initialize the property value for the `DBPROP` structure added to the property set.  
  
 `cyValue`  
 \[in\] A CY currency value used to initialize the property value for the `DBPROP` structure added to the property set.  
  
## 반환 값  
 **true** if the property was successfully added.  그렇지 않으면 **false**입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDBPropSet 클래스](../../data/oledb/cdbpropset-class.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)