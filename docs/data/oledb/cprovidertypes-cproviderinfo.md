---
title: CProviderTypes, CProviderInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_bIsLong
- m_szLocalTypeName
- m_guidType
- m_bCaseSensitive
- m_szVersion
- m_szCreateParams
- IS_NULLABLE
- m_bAutoUniqueValue
- LITERAL_SUFFIX
- COLUMN_SIZE
- CProviderTypes
- LOCAL_TYPE_NAME
- MINIMUM_SCALE
- m_nMinScale
- m_nColumnSize
- m_szLiteralSuffix
- m_bFixedPrecScale
- m_szLiteralPrefix
- m_nMaxScale
- m_szTypeLib
- m_nDataType
- m_bUnsignedAttribute
- m_nSearchable
- m_bBestMatch
- m_szTypeName
- DATA_TYPE
- MAXIMUM_SCALE
- CProviderInfo
- FIXED_PREC_SCALE
- m_bIsNullable
- IS_LONG
dev_langs:
- C++
helpviewer_keywords:
- DATA_TYPE
- MAXIMUM_SCALE
- m_nMinScale
- m_guidType
- LOCAL_TYPE_NAME
- m_bAutoUniqueValue
- m_bBestMatch
- m_bIsLong
- m_bUnsignedAttribute
- CProviderInfo parameter class
- FIXED_PREC_SCALE
- m_nColumnSize
- m_szVersion
- CProviderTypes typedef class
- m_szCreateParams
- IS_NULLABLE
- m_bIsNullable
- m_szTypeLib
- m_szLiteralPrefix
- m_nMaxScale
- m_nDataType
- m_bCaseSensitive
- m_bFixedPrecScale
- m_nSearchable
- MINIMUM_SCALE
- m_szTypeName
- m_szLocalTypeName
- IS_LONG
- LITERAL_SUFFIX
- COLUMN_SIZE
- m_szLiteralSuffix
ms.assetid: 6f1620ff-c2f0-4f5b-931c-27b0cd2a580d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5937d45a49cce84f8c9db55bd6a1b18a51b60ee6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cprovidertypes-cproviderinfo"></a>CProviderTypes, CProviderInfo
Typedef 클래스 호출 **CProviderTypes** 해당 매개 변수 클래스를 구현 하려면 **CProviderInfo**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef 클래스 사용에 대 한 자세한 내용은 합니다.  
  
 이 클래스는 데이터 공급자가 지 원하는 기본 데이터 형식을 식별 합니다.  
  
 다음 표에는 클래스 데이터 멤버 및 해당 OLE DB 열이 나열됩니다. 참조 [PROVIDER_TYPES 행 집합](https://msdn.microsoft.com/en-us/library/ms709785.aspx) 에 *OLE DB Programmer's Reference* 스키마 및 열에 대 한 자세한 내용은 합니다.  
  
|데이터 멤버|OLE DB 열|  
|------------------|--------------------|  
|m_szTypeName|TYPE_NAME|  
|m_nDataType|DATA_TYPE|  
|m_nColumnSize|COLUMN_SIZE|  
|m_szLiteralPrefix|LITERAL_PREFIX|  
|m_szLiteralSuffix|LITERAL_SUFFIX|  
|m_szCreateParams|CREATE_PARAMS|  
|m_bIsNullable|IS_NULLABLE|  
|m_bCaseSensitive|CASE_SENSITIVE|  
|m_nSearchable|검색 가능한|  
|m_bUnsignedAttribute|UNSIGNED_ATTRIBUTE|  
|m_bFixedPrecScale|FIXED_PREC_SCALE|  
|m_bAutoUniqueValue|AUTO_UNIQUE_VALUE|  
|m_szLocalTypeName|LOCAL_TYPE_NAME|  
|m_nMinScale|MINIMUM_SCALE|  
|m_nMaxScale|MAXIMUM_SCALE|  
|m_guidType|GUID|  
|m_szTypeLib|형식 라이브러리|  
|m_szVersion|VERSION|  
|m_bIsLong|IS_LONG|  
|m_bBestMatch|BEST_MATCH|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)