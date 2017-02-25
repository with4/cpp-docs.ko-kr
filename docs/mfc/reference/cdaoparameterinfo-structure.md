---
title: "CDaoParameterInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoParameterInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoParameterInfo 구조체"
  - "DAO(Data Access Objects), 매개 변수 컬렉션"
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoParameterInfo 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `CDaoParameterInfo` structure contains information about a parameter object defined for data access objects \(DAO\).  
  
## 구문  
  
```  
  
      struct CDaoParameterInfo  
{  
   CString m_strName;       // Primary  
   short m_nType;           // Primary  
   ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### 매개 변수  
 `m_strName`  
 Uniquely names the parameter object.  For more information, see the topic "Name Property" in DAO Help.  
  
 `m_nType`  
 A value that indicates the data type of a parameter object.  For a list of the possible values, see the `m_nType` member of the [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) structure.  For more information, see the topic "Type Property" in DAO Help.  
  
 *m\_varValue*  
 The value of the parameter, stored in a [COleVariant](../../mfc/reference/colevariant-class.md) object.  
  
## 설명  
 The references to Primary and Secondary above indicate how the information is returned by the [GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) member function in class `CDaoQueryDef`.  
  
 MFC does not encapsulate DAO parameter objects in a class.  DAO querydef objects underlying MFC `CDaoQueryDef` objects store parameters in their Parameters collections.  To access the parameter objects in a [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) object, call the querydef object's `GetParameterInfo` member function for a particular parameter name or an index into the Parameters collection.  You can use the [CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md) member function in conjunction with `GetParameterInfo` to loop through the Parameters collection.  
  
 Information retrieved by the [CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) member function is stored in a `CDaoParameterInfo` structure.  Call `GetParameterInfo` for the querydef object in whose Parameters collection the parameter object is stored.  
  
> [!NOTE]
>  If you want to get or set only the value of a parameter, use the [GetParamValue](../Topic/CDaoRecordset::GetParamValue.md) and [SetParamValue](../Topic/CDaoRecordset::SetParamValue.md) member functions of class `CDaoRecordset`.  
  
 `CDaoParameterInfo` also defines a `Dump` member function in debug builds.  You can use `Dump` to dump the contents of a `CDaoParameterInfo` object.  
  
## 요구 사항  
 **Header:** afxdao.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)