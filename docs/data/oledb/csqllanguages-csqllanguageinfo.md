---
title: "CSQLLanguages, CSQLLanguageInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSQLLanguageInfo"
  - "m_szProgrammingLanguage"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szSource"
  - "m_szYear"
  - "CSQLLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSQLLanguageInfo 매개 변수 클래스"
  - "CSQLLanguages typedef 클래스"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szProgrammingLanguage"
  - "m_szSource"
  - "m_szYear"
ms.assetid: 9c36c5bb-6917-49c3-9ac3-942339893f19
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CSQLLanguages, CSQLLanguageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CSQLLanguages** to implement its parameter class **CSQLLanguageInfo**.  
  
## 설명  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the conformance levels, options, and dialects supported by the SQL\-implementation processing data defined in the catalog.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [SQL\_LANGUAGES Rowset](https://msdn.microsoft.com/en-us/library/ms714374.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szSource|SQL\_LANGUAGE\_SOURCE|  
|m\_szYear|SQL\_LANGUAGE\_YEAR|  
|m\_szConformance|SQL\_LANGUAGE\_CONFORMANCE|  
|m\_szIntegrity|SQL\_LANGUAGE\_INTEGRITY|  
|m\_szImplementation|SQL\_LANGUAGE\_IMPLEMENTATION|  
|m\_szBindingStyle|SQL\_LANGUAGE\_BINDING\_STYLE|  
|m\_szProgrammingLanguage|SQL\_LANGUAGE\_PROGRAMMING\_LANGUAGE|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)