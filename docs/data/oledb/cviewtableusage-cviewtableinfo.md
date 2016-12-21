---
title: "CViewTableUsage, CViewTableInfo | Microsoft Docs"
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
  - "m_szTableSchema"
  - "m_szCatalog"
  - "CViewTableInfo"
  - "m_szTableCatalog"
  - "m_szSchema"
  - "m_szTableName"
  - "m_szName"
  - "CViewTableUsage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CViewTableInfo 매개 변수 클래스"
  - "CViewTableUsage typedef 클래스"
  - "m_szCatalog"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 10b74f2a-8010-4f97-acc2-ffce07349981
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CViewTableUsage, CViewTableInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

그들의 매개 변수 클래스 **CViewTableInfo**를 구현하기 위해서 typedef 클래스 **CViewTableUsage**를 호출합니다.  
  
## 설명  
 typedef 클래스를 사용하는 것에 대한 자세한 내용은 [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)를 참조하십시오.  
  
 이 클래스는 지정된 사용자가 액세스 가능하며 카탈로그에 정의된 보이는 표를 식별합니다.  
  
 다음 표는 클래스 데이터 멤버 및 그들의 해당 OLE DB 열을 열거합니다.  스키마 및 열에 대한 추가 정보는, *OLE DB Programmer's Reference*에서 [VIEW\_TABLE\_USAGE Rowset](https://msdn.microsoft.com/en-us/library/ms719727.aspx)를 참조하십시오.  
  
|데이터 멤버|OLE DB 열|  
|------------|--------------|  
|m\_szCatalog|VIEW\_CATALOG|  
|m\_szSchema|VIEW\_SCHEMA|  
|m\_szName|VIEW\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)