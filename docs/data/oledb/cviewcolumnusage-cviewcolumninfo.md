---
title: CViewColumnUsage, CViewColumnInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_szCatalog
- m_nColumnPropID
- COLUMN_GUID
- m_szColumnName
- m_szTableCatalog
- CViewColumnInfo
- m_szSchema
- CViewColumnUsage
- COLUMN_PROPID
- m_guidColumn
- m_szTableName
- m_szName
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szSchema
- m_szTableSchema
- TABLE_CATALOG
- m_szCatalog
- TABLE_NAME
- m_nColumnPropID
- CViewColumnInfo parameter class
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szName
- m_szTableCatalog
- CViewColumnUsage typedef class
- m_szTableName
- COLUMN_GUID
- m_guidColumn
ms.assetid: 4af14d6b-b224-4d72-b035-9d3aaacde32f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4845af212cd7c2cd7a542cd2b23eed6c8991c1da
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cviewcolumnusage-cviewcolumninfo"></a>CViewColumnUsage, CViewColumnInfo
Typedef 클래스 호출 **CViewColumnUsage** 해당 매개 변수 클래스를 구현 하려면 **CViewColumnInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스에서는 열에 카탈로그에 정의 된 테이블을 표시 하 고 종속 되어 지정된 된 사용자가 소유 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [VIEW_COLUMN_USAGE 행 집합](https://msdn.microsoft.com/en-us/library/ms714896.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szCatalog|VIEW_CATALOG|  
|m_szSchema|VIEW_SCHEMA|  
|m_szName|VIEW_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)