---
title: CForeignKeys, CForeignKeysInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_nOrdinal
- m_szPKColumnName
- FK_TABLE_NAME
- m_guidFKColumn
- FK_COLUMN_NAME
- m_guidPKColumn
- DELETE_RULE
- m_szPKTableSchema
- FK_COLUMN_PROPID
- m_nFKColumnPropID
- m_szFKTableCatalog
- CForeignKeysInfo
- FK_TABLE_SCHEMA
- m_szPKTableCatalog
- m_szDeleteRule
- m_szUpdateRule
- m_szPKTableName
- m_szFKTableSchema
- ORDINAL
- m_nPKColumnPropID
- m_szFKColumnName
- FK_TABLE_CATALOG
- FK_COLUMN_GUID
- m_szFKTableName
- CForeignKeys
dev_langs:
- C++
helpviewer_keywords:
- m_szPKTableCatalog
- FK_COLUMN_GUID
- m_szPKColumnName
- m_szFKTableName
- ORDINAL data member
- m_nPKColumnPropID
- m_szDeleteRule
- DELETE_RULE
- m_guidFKColumn
- FK_COLUMN_PROPID
- m_szPKTableSchema
- m_szFKTableCatalog
- CForeignKeysInfo parameter class
- m_szFKTableSchema
- FK_TABLE_SCHEMA
- FK_COLUMN_NAME
- m_szUpdateRule
- m_szFKColumnName
- FK_TABLE_CATALOG
- m_nOrdinal
- m_szPKTableName
- CForeignKeys typedef class
- m_nFKColumnPropID
- m_guidPKColumn
- FK_TABLE_NAME
ms.assetid: 1c401a4a-0827-4255-9214-bc893e1cd79d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e15b4a855375161f15ff9fa872a700f93b817a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cforeignkeys-cforeignkeysinfo"></a>CForeignKeys, CForeignKeysInfo
Typedef 클래스 호출 **CForeignKeys** 해당 매개 변수 클래스를 구현 하려면 **CForeignKeysInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스는 지정된 된 사용자가 카탈로그에 정의 된 외래 키 열을 식별 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [FOREIGN_KEYS 행 집합](https://msdn.microsoft.com/en-us/library/ms711276.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szPKTableCatalog|PK_TABLE_CATALOG|  
|m_szPKTableSchema|PK_TABLE_SCHEMA|  
|m_szPKTableName|PK_TABLE_NAME|  
|m_szPKColumnName|PK_COLUMN_NAME|  
|m_guidPKColumn|PK_COLUMN_GUID|  
|m_nPKColumnPropID|PK_COLUMN_PROPID|  
|m_szFKTableCatalog|FK_TABLE_CATALOG|  
|m_szFKTableSchema|FK_TABLE_SCHEMA|  
|m_szFKTableName|FK_TABLE_NAME|  
|m_szFKColumnName|FK_COLUMN_NAME|  
|m_guidFKColumn|FK_COLUMN_GUID|  
|m_nFKColumnPropID|FK_COLUMN_PROPID|  
|m_nOrdinal|서 수|  
|m_szUpdateRule|UPDATE_RULE|  
|m_szDeleteRule|DELETE_RULE|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)