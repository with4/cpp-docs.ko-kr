---
title: CIndexes, CIndexInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- INITIAL_SIZE
- NULL_COLLATION
- m_szFilterCondition
- m_bPrimaryKey
- m_szTableSchema
- m_bSortBookmarks
- m_szIndexSchema
- m_nColumnPropID
- ORDINAL_POSITION
- INDEX_CATALOG
- m_nOrdinalPosition
- COLUMN_GUID
- m_bAutoUpdate
- m_nNullCollation
- CLUSTERED
- NULLS
- m_szColumnName
- m_nFillFactor
- m_nPages
- INDEX_NAME
- m_szTableCatalog
- m_szIndexName
- m_szIndexCatalog
- m_nCardinality
- m_nInitialSize
- m_bUnique
- COLUMN_PROPID
- m_guidColumn
- m_nNulls
- m_szTableName
- FILL_FACTOR
- m_nType
- m_bClustered
- COLLATION
- FILTER_CONDITION
- m_nCollation
- CIndexes
- INDEX_SCHEMA
- CIndexInfo
dev_langs: C++
helpviewer_keywords:
- COLUMN_PROPID
- ORDINAL_POSITION
- INDEX_CATALOG
- NULLS
- CIndexInfo parameter class
- m_szFilterCondition
- m_szIndexCatalog
- CLUSTERED
- m_nType
- FILL_FACTOR
- m_nPages
- m_nCardinality
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- INDEX_SCHEMA
- m_nInitialSize
- m_nOrdinalPosition
- m_nColumnPropID
- FILTER_CONDITION
- TABLE_SCHEMA
- m_szColumnName
- INDEX_NAME
- NULL_COLLATION
- m_bUnique
- m_bSortBookmarks
- m_bAutoUpdate
- COLUMN_NAME
- INITIAL_SIZE
- m_szTableCatalog
- m_nNullCollation
- m_bClustered
- m_szTableName
- CIndexes typedef class
- m_nCollation
- COLUMN_GUID
- m_guidColumn
- m_nNulls
- m_bPrimaryKey
- m_szIndexName
- m_nFillFactor
- m_szIndexSchema
ms.assetid: 592fa773-fd23-4332-8d47-d76101f9ddd7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c051e233c15959f71d57fa6eef1e398257b6d51f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cindexes-cindexinfo"></a>CIndexes, CIndexInfo
Typedef 클래스 호출 **CIndexes** 해당 매개 변수 클래스를 구현 하려면 **CIndexInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스는 인덱스는 카탈로그에 정의 된 지정된 된 사용자가 소유 하 고 있는 식별 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [인덱스 행 집합](https://msdn.microsoft.com/en-us/library/ms709712.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szIndexCatalog|INDEX_CATALOG|  
|m_szIndexSchema|INDEX_SCHEMA|  
|m_szIndexName|INDEX_NAME|  
|m_bPrimaryKey|PRIMARY_KEY|  
|m_bUnique|UNIQUE|  
|m_bClustered|CLUSTERED|  
|m_nType|TYPE|  
|m_nFillFactor|FILL_FACTOR|  
|m_nInitialSize|INITIAL_SIZE|  
|m_nNulls|NULLS|  
|m_bSortBookmarks|SORT_BOOKMARKS|  
|m_bAutoUpdate|AUTO_UPDATE|  
|m_nNullCollation|NULL_COLLATION|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_nCollation|COLLATION|  
|m_nCardinality|CARDINALITY|  
|m_nPages|PAGES|  
|m_szFilterCondition|FILTER_CONDITION|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)