---
title: CViewTableUsage, CViewTableInfo | Microsoft Docs
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
- CViewTableInfo
- m_szTableCatalog
- m_szSchema
- m_szTableName
- m_szName
- CViewTableUsage
dev_langs:
- C++
helpviewer_keywords:
- CViewTableInfo parameter class
- CViewTableUsage typedef class
- m_szSchema
- m_szTableSchema
- TABLE_CATALOG
- m_szCatalog
- TABLE_NAME
- TABLE_SCHEMA
- m_szName
- m_szTableCatalog
- m_szTableName
ms.assetid: 10b74f2a-8010-4f97-acc2-ffce07349981
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 470a7be46c5afbae5f6d3a1fb88377e56ea0e1fa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cviewtableusage-cviewtableinfo"></a>CViewTableUsage, CViewTableInfo
Typedef 클래스 호출 **CViewTableUsage** 해당 매개 변수 클래스를 구현 하려면 **CViewTableInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스는 본된 테이블 카탈로그에 정의 된 지정된 된 사용자에 액세스할 수 있는 식별 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [VIEW_TABLE_USAGE 행 집합](https://msdn.microsoft.com/en-us/library/ms719727.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szCatalog|VIEW_CATALOG|  
|m_szSchema|VIEW_SCHEMA|  
|m_szName|VIEW_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)