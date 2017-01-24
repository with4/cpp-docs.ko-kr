---
title: "CProviderTypes, CProviderInfo | Microsoft Docs"
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
  - "m_bIsLong"
  - "m_szLocalTypeName"
  - "m_guidType"
  - "m_bCaseSensitive"
  - "m_szVersion"
  - "m_szCreateParams"
  - "IS_NULLABLE"
  - "m_bAutoUniqueValue"
  - "LITERAL_SUFFIX"
  - "COLUMN_SIZE"
  - "CProviderTypes"
  - "LOCAL_TYPE_NAME"
  - "MINIMUM_SCALE"
  - "m_nMinScale"
  - "m_nColumnSize"
  - "m_szLiteralSuffix"
  - "m_bFixedPrecScale"
  - "m_szLiteralPrefix"
  - "m_nMaxScale"
  - "m_szTypeLib"
  - "m_nDataType"
  - "m_bUnsignedAttribute"
  - "m_nSearchable"
  - "m_bBestMatch"
  - "m_szTypeName"
  - "DATA_TYPE"
  - "MAXIMUM_SCALE"
  - "CProviderInfo"
  - "FIXED_PREC_SCALE"
  - "m_bIsNullable"
  - "IS_LONG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_SIZE"
  - "CProviderInfo 매개 변수 클래스"
  - "CProviderTypes typedef 클래스"
  - "DATA_TYPE"
  - "FIXED_PREC_SCALE"
  - "IS_LONG"
  - "IS_NULLABLE"
  - "LITERAL_SUFFIX"
  - "LOCAL_TYPE_NAME"
  - "m_bAutoUniqueValue"
  - "m_bBestMatch"
  - "m_bCaseSensitive"
  - "m_bFixedPrecScale"
  - "m_bIsLong"
  - "m_bIsNullable"
  - "m_bUnsignedAttribute"
  - "m_guidType"
  - "m_nColumnSize"
  - "m_nDataType"
  - "m_nMaxScale"
  - "m_nMinScale"
  - "m_nSearchable"
  - "m_szCreateParams"
  - "m_szLiteralPrefix"
  - "m_szLiteralSuffix"
  - "m_szLocalTypeName"
  - "m_szTypeLib"
  - "m_szTypeName"
  - "m_szVersion"
  - "MAXIMUM_SCALE"
  - "MINIMUM_SCALE"
ms.assetid: 6f1620ff-c2f0-4f5b-931c-27b0cd2a580d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CProviderTypes, CProviderInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CProviderTypes** to implement its parameter class **CProviderInfo**.  
  
## 설명  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the \(base\) data types supported by the data provider.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [PROVIDER\_TYPES Rowset](https://msdn.microsoft.com/en-us/library/ms709785.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szTypeName|TYPE\_NAME|  
|m\_nDataType|DATA\_TYPE|  
|m\_nColumnSize|COLUMN\_SIZE|  
|m\_szLiteralPrefix|LITERAL\_PREFIX|  
|m\_szLiteralSuffix|LITERAL\_SUFFIX|  
|m\_szCreateParams|CREATE\_PARAMS|  
|m\_bIsNullable|IS\_NULLABLE|  
|m\_bCaseSensitive|CASE\_SENSITIVE|  
|m\_nSearchable|SEARCHABLE|  
|m\_bUnsignedAttribute|UNSIGNED\_ATTRIBUTE|  
|m\_bFixedPrecScale|FIXED\_PREC\_SCALE|  
|m\_bAutoUniqueValue|AUTO\_UNIQUE\_VALUE|  
|m\_szLocalTypeName|LOCAL\_TYPE\_NAME|  
|m\_nMinScale|MINIMUM\_SCALE|  
|m\_nMaxScale|MAXIMUM\_SCALE|  
|m\_guidType|GUID|  
|m\_szTypeLib|TYPELIB|  
|m\_szVersion|VERSION|  
|m\_bIsLong|IS\_LONG|  
|m\_bBestMatch|BEST\_MATCH|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)