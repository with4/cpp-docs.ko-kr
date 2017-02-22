---
title: "CDaoRelationFieldInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoRelationFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRelationFieldInfo 구조체"
  - "DAO(Data Access Objects), 관계 컬렉션"
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoRelationFieldInfo 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `CDaoRelationFieldInfo` structure contains information about a field in a relation defined for data access objects \(DAO\).  
  
## 구문  
  
```  
  
      struct CDaoRelationFieldInfo  
{  
   CString m_strName;           // Primary  
   CString m_strForeignName;    // Primary  
};  
```  
  
#### 매개 변수  
 `m_strName`  
 The name of the field in the primary table of the relation.  
  
 `m_strForeignName`  
 The name of the field in the foreign table of the relation.  
  
## 설명  
 A DAO relation object specifies the fields in a primary table and the fields in a foreign table that define the relation.  The references to Primary in the structure definition above indicate how the information is returned in the `m_pFieldInfos` member of a [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) object obtained by calling the [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) member function of class `CDaoDatabase`.  
  
 Relation objects and relation field objects are not represented by an MFC class.  Instead, the DAO objects underlying MFC objects of class [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) contain a collection of relation objects, called the Relations collection.  Each relation object, in turn, contains a collection of relation field objects.  Each relation field object correlates a field in the primary table with a field in the foreign table.  Taken together, the relation field objects define a group of fields in each table, which together define the relation.  `CDaoDatabase` lets you access relation objects with a `CDaoRelationInfo` object by calling the `GetRelationInfo` member function.  The `CDaoRelationInfo` object, then, has a data member, `m_pFieldInfos`, that points to an array of `CDaoRelationFieldInfo` objects.  
  
 Call the [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) member function of the containing `CDaoDatabase` object in whose Relations collection is stored the relation object you are interested in.  Then access the `m_pFieldInfos` member of the [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) object.  `CDaoRelationFieldInfo` also defines a `Dump` member function in debug builds.  You can use `Dump` to dump the contents of a `CDaoRelationFieldInfo` object.  
  
## 요구 사항  
 **Header:** afxdao.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo 구조체](../../mfc/reference/cdaorelationinfo-structure.md)