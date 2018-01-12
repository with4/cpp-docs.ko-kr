---
title: CConstraintTableUsage, CConstraintTableUsageInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CConstraintTableUsageInfo
- CONSTRAINT_TABLE_USAGE
- m_szTableSchema
- m_szConstraintCatalog
- CONSTRAINT_NAME
- m_szTableCatalog
- m_szConstraintSchema
- m_szTableName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- CConstraintTableUsage
- m_szConstraintName
dev_langs: C++
helpviewer_keywords:
- CConstraintTableUsage typedef class
- m_szConstraintCatalog
- CONSTRAINT_CATALOG
- m_szTableSchema
- CConstraintTableUsageInfo parameter class
- TABLE_CATALOG
- CONSTRAINT_TABLE_USAGE
- TABLE_NAME
- CONSTRAINT_NAME
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szTableCatalog
- m_szConstraintName
- m_szTableName
- m_szConstraintSchema
ms.assetid: 666b44de-3922-4c5e-ad17-d5ea27120174
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf806ac79d74a3ce0ba265722a1633854d925778
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cconstrainttableusage-cconstrainttableusageinfo"></a>CConstraintTableUsage, CConstraintTableUsageInfo
Typedef 클래스 호출 **CConstraintTableUsage** 해당 매개 변수 클래스를 구현 하려면 **CConstraintTableUsageInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스는 참조 제약 조건, unique 제약 조건, check 제약 조건 및 어설션을 사용 하 고 카탈로그에 정의 된 지정된 된 사용자가 소유 하 고 테이블을 식별 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [CONSTRAINT_TABLE_USAGE 행 집합](https://msdn.microsoft.com/en-us/library/ms724522.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szConstraintCatalog|CONSTRAINT_CATALOG|  
|m_szConstraintSchema|CONSTRAINT_SCHEMA|  
|m_szConstraintName|CONSTRAINT_NAME|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)