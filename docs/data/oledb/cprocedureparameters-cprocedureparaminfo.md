---
title: CProcedureParameters CProcedureParamInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_szDefault
- CProcedureParameters
- m_bHasDefault
- CProcedureParamInfo
- IS_NULLABLE
- m_szCatalog
- ORDINAL_POSITION
- m_nOrdinalPosition
- NUMERIC_PRECISION
- m_nDataType
- m_szSchema
- CHARACTER_OCTET_LENGTH
- NUMERIC_SCALE
- m_szParameterName
- m_nMaxLength
- CHARACTER_MAXIMUM_LENGTH
- m_nPrecision
- m_szName
- DATA_TYPE
- m_nOctetLength
- m_nType
- m_bIsNullable
- m_nScale
dev_langs:
- C++
helpviewer_keywords:
- NUMERIC_PRECISION
- DATA_TYPE
- ORDINAL_POSITION
- m_nMaxLength
- DESCRIPTION class data member
- m_szParameterName
- m_szSchema
- m_nType
- m_bHasDefault
- CHARACTER_OCTET_LENGTH
- CProcedureParameters typedef class
- m_szCatalog
- m_nPrecision
- m_nOrdinalPosition
- NUMERIC_SCALE
- m_nOctetLength
- IS_NULLABLE
- m_szName
- m_bIsNullable
- CProcedureParamInfo parameter class
- m_szDescription
- m_szDefault
- m_nDataType
- m_nScale
- CHARACTER_MAXIMUM_LENGTH
ms.assetid: 61f8d55a-684a-47a3-b102-068cc3f52d84
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1040f3a02af60afda8796ba241922d691068a5ea
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cprocedureparameters-cprocedureparaminfo"></a>CProcedureParameters CProcedureParamInfo
Typedef 클래스 호출 **CProcedureParameters** 해당 매개 변수 클래스를 구현 하려면 **CProcedureParamInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스의 매개 변수와 프로시저 반환 코드에 대 한 정보를 반환합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [PROCEDURE_PARAMETERS 행 집합](https://msdn.microsoft.com/en-us/library/ms713623.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szCatalog|PROCEDURE_CATALOG|  
|m_szSchema|PROCEDURE_SCHEMA|  
|m_szName|PROCEDURE_NAME|  
|m_szParameterName|PARAMETER_NAME|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
|m_nType|PARAMETER_TYPE|  
|m_bHasDefault|PARAMETER_HASDEFAULT|  
|m_szDefault|PARAMETER_DEFAULT|  
|m_bIsNullable|IS_NULLABLE|  
|m_nDataType|DATA_TYPE|  
|m_nMaxLength|CHARACTER_MAXIMUM_LENGTH|  
|m_nOctetLength|CHARACTER_OCTET_LENGTH|  
|m_nPrecision|NUMERIC_PRECISION|  
|m_nScale|NUMERIC_SCALE|  
|m_szDescription|설명|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)