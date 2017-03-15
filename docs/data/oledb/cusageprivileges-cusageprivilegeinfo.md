---
title: "CUsagePrivileges, CUsagePrivilegeInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szObjectCatalog"
  - "CUsagePrivilegeInfo"
  - "m_bIsGrantable"
  - "OBJECT_NAME"
  - "m_szPrivilegeType"
  - "OBJECT_SCHEMA"
  - "IS_GRANTABLE"
  - "CUsagePrivileges"
  - "m_szGrantor"
  - "GRANTOR"
  - "GRANTEE"
  - "m_szObjectSchema"
  - "OBJECT_CATALOG"
  - "m_szObjectType"
  - "m_szObjectName"
  - "m_szGrantee"
  - "OBJECT_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUsagePrivilegeInfo 매개 변수 클래스"
  - "CUsagePrivileges typedef 클래스"
  - "GRANTEE"
  - "GRANTOR"
  - "IS_GRANTABLE"
  - "m_bIsGrantable"
  - "m_szGrantee"
  - "m_szGrantor"
  - "m_szObjectCatalog"
  - "m_szObjectName"
  - "m_szObjectSchema"
  - "m_szObjectType"
  - "m_szPrivilegeType"
  - "OBJECT_CATALOG"
  - "OBJECT_NAME"
  - "OBJECT_SCHEMA"
  - "OBJECT_TYPE"
ms.assetid: 09460e7f-3947-4837-ad1e-407b94acedb8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CUsagePrivileges, CUsagePrivilegeInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**CUsagePrivileges** 클래스의 typedef를 호출하여 **CUsagePrivilegeInfo** 클래스 매개 변수를 구현하십시오.  
  
## 설명  
 typedef 클래스를 사용하는 것에 대한 자세한 내용은 [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)를 참조하십시오.  
  
 이 클래스는 지정된 사용자가 사용할 수 있거나 지정된 사용자가 승인한 카탈로그에서 정의된 개체에 대한 USAGE 권한을 식별합니다.  
  
 다음 표는 클래스 데이터 멤버 및 그들의 해당 OLE DB 열을 열거합니다.  스키마와 열에 대한 자세한 정보를 *OLE DB Programmer's Reference* 에서 [USAGE\_PRIVILEGES Rowset](https://msdn.microsoft.com/en-us/library/ms722743.aspx) 를 참조하십시오.  
  
|데이터 멤버|OLE DB 열|  
|------------|--------------|  
|m\_szGrantor|GRANTOR|  
|m\_szGrantee|GRANTEE|  
|m\_szObjectCatalog|OBJECT\_CATALOG|  
|m\_szObjectSchema|OBJECT\_SCHEMA|  
|m\_szObjectName|OBJECT\_NAME|  
|m\_szObjectType|OBJECT\_TYPE|  
|m\_szPrivilegeType|PRIVILEGE\_TYPE|  
|m\_bIsGrantable|IS\_GRANTABLE|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)