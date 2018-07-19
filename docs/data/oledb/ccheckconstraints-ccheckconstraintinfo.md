---
title: CCheckConstraints, CCheckConstraintInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCheckConstraintInfo
- CHECK_CONSTRAINTS
- m_szCatalog
- CCheckConstraints
- CONSTRAINT_NAME
- m_szSchema
- CHECK_CLAUSE
- m_szCheckClause
- m_szName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- m_szSchema
- CONSTRAINT_CATALOG
- m_szCatalog
- CONSTRAINT_NAME
- CONSTRAINT_SCHEMA
- CCheckConstraints typedef class
- CHECK_CLAUSE
- m_szName
- m_szDescription
- CCheckConstraintInfo parameter class
- m_szCheckClause
- CHECK_CONSTRAINTS
ms.assetid: e53e79a5-01e5-42b7-aa8c-164aec94b011
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2f167212458266b44f93315cd3185010461c78d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093872"
---
# <a name="ccheckconstraints-ccheckconstraintinfo"></a>CCheckConstraints, CCheckConstraintInfo
Typedef 클래스 호출 **CCheckConstraints** 해당 매개 변수 클래스를 구현 하려면 **CCheckConstraintInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스는 check 제약 조건에는 카탈로그에 정의 된 지정된 된 사용자가 소유 하는 식별 합니다. Check 제약 조건에는 데이터 값 또는 테이블의 하나 이상의 열에 사용할 수 있는 형식을 지정 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [CHECK_CONSTRAINTS 행 집합](https://msdn.microsoft.com/en-us/library/ms712845.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szCheckClause|CHECK_CLAUSE|  
|m_szDescription|설명|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)