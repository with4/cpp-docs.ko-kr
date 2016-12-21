---
title: "PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs"
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
  - "PROPERTY_INFO_ENTRY_VALUE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE 매크로"
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROPERTY_INFO_ENTRY_VALUE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a specific property in a property set.  
  
## 구문  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### 매개 변수  
 *dwPropID*  
 \[in\] A [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) value that can be used in conjunction with the property set GUID to identify a property.  
  
 *value*  
 \[in\] The property value of type `DWORD`.  
  
## 설명  
 With this macro, you can directly specify the property value of type `DWORD`.  To set the property to default value defined in ATLDB.H, use [PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md).  To set the value, flags, and options for the property, use [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## 예제  
 See [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)