---
title: "CAssertions, CAssertionInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAssertions"
  - "m_szCatalog"
  - "m_bInitiallyDeferred"
  - "CONSTRAINT_NAME"
  - "m_szSchema"
  - "INITIALLY_DEFERRED"
  - "m_bIsDeferrable"
  - "m_szName"
  - "CAssertionInfo"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "IS_DEFERRABLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAssertionInfo 매개 변수 클래스"
  - "CAssertions typedef 클래스"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "DESCRIPTION 클래스 데이터 멤버"
  - "INITIALLY_DEFERRED"
  - "IS_DEFERRABLE"
  - "m_bInitiallyDeferred"
  - "m_bIsDeferrable"
  - "m_szCatalog"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
ms.assetid: 2a79c2da-5c9b-4fa6-98e8-90b7f5d6f021
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CAssertions, CAssertionInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typedef  클래스 **CAssertions**를 호출하여  매개 변수 클래스 **CAssertionInfo**를 구현합니다.  
  
## 설명  
 typedef 클래스를 사용하는 것에 대한 자세한 내용은 [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)를 참조하십시오.  
  
 이 클래스는 지정된 사용자가 소유하고있는 카탈로그에 정의 된 어설 션을 식별합니다.  
  
 다음 표는 **CAssertionInfo**와 해당 OLE DB 컬럼의 클래스 데이터 멤버를 보여줍니다.  스키마와 열에 대한 자세한 정보를 *OLE DB Programmer's Reference* 에서 [ASSERTIONS  Rowset](https://msdn.microsoft.com/en-us/library/ms719776.aspx) 를 참조하십시오.  
  
|데이터 멤버|OLE DB 열|  
|------------|--------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_bIsDeferrable|IS\_DEFERRABLE|  
|m\_bInitiallyDeferred|INITIALLY\_DEFERRED|  
|m\_szDescription|DESCRIPTION|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)