---
title: "CForeignKeys, CForeignKeysInfo | Microsoft Docs"
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
  - "m_nOrdinal"
  - "m_szPKColumnName"
  - "FK_TABLE_NAME"
  - "m_guidFKColumn"
  - "FK_COLUMN_NAME"
  - "m_guidPKColumn"
  - "DELETE_RULE"
  - "m_szPKTableSchema"
  - "FK_COLUMN_PROPID"
  - "m_nFKColumnPropID"
  - "m_szFKTableCatalog"
  - "CForeignKeysInfo"
  - "FK_TABLE_SCHEMA"
  - "m_szPKTableCatalog"
  - "m_szDeleteRule"
  - "m_szUpdateRule"
  - "m_szPKTableName"
  - "m_szFKTableSchema"
  - "ORDINAL"
  - "m_nPKColumnPropID"
  - "m_szFKColumnName"
  - "FK_TABLE_CATALOG"
  - "FK_COLUMN_GUID"
  - "m_szFKTableName"
  - "CForeignKeys"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CForeignKeys typedef 클래스"
  - "CForeignKeysInfo 매개 변수 클래스"
  - "DELETE_RULE"
  - "FK_COLUMN_GUID"
  - "FK_COLUMN_NAME"
  - "FK_COLUMN_PROPID"
  - "FK_TABLE_CATALOG"
  - "FK_TABLE_NAME"
  - "FK_TABLE_SCHEMA"
  - "m_guidFKColumn"
  - "m_guidPKColumn"
  - "m_nFKColumnPropID"
  - "m_nOrdinal"
  - "m_nPKColumnPropID"
  - "m_szDeleteRule"
  - "m_szFKColumnName"
  - "m_szFKTableCatalog"
  - "m_szFKTableName"
  - "m_szFKTableSchema"
  - "m_szPKColumnName"
  - "m_szPKTableCatalog"
  - "m_szPKTableName"
  - "m_szPKTableSchema"
  - "m_szUpdateRule"
  - "ORDINAL 데이터 멤버"
ms.assetid: 1c401a4a-0827-4255-9214-bc893e1cd79d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CForeignKeys, CForeignKeysInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이것의 매개변수 클래스 **CForeignKeysInfo** 를 구현하기 위해 typedef 클래스 **CForeignKeys** 를 호출합니다.  
  
## 설명  
 typedef 클래스를 사용하는 것에 대한 자세한 내용은 [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)를 참조하십시오.  
  
 이 클래스는 지정된 사용자가 카탈로그에서 정의한 외부 키 열을 식별합니다.  
  
 다음 표는 클래스 데이터 멤버 및 그들의 해당 OLE DB 열을 열거합니다.  스키마와 열에 대한 자세한 정보에 대하여, *OLE DB Programmer's Reference* 에서 [FOREIGN\_KEYS Rowset](https://msdn.microsoft.com/en-us/library/ms711276.aspx)를 참고하세요.  
  
|데이터 멤버|OLE DB 열|  
|------------|--------------|  
|m\_szPKTableCatalog|PK\_TABLE\_CATALOG|  
|m\_szPKTableSchema|PK\_TABLE\_SCHEMA|  
|m\_szPKTableName|PK\_TABLE\_NAME|  
|m\_szPKColumnName|PK\_COLUMN\_NAME|  
|m\_guidPKColumn|PK\_COLUMN\_GUID|  
|m\_nPKColumnPropID|PK\_COLUMN\_PROPID|  
|m\_szFKTableCatalog|FK\_TABLE\_CATALOG|  
|m\_szFKTableSchema|FK\_TABLE\_SCHEMA|  
|m\_szFKTableName|FK\_TABLE\_NAME|  
|m\_szFKColumnName|FK\_COLUMN\_NAME|  
|m\_guidFKColumn|FK\_COLUMN\_GUID|  
|m\_nFKColumnPropID|FK\_COLUMN\_PROPID|  
|m\_nOrdinal|서수|  
|m\_szUpdateRule|업데이트 규칙|  
|m\_szDeleteRule|DELETE\_RULE|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)