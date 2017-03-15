---
title: "CCharacterSets, CCharacterSetInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szCollateName"
  - "m_szCatalog"
  - "DEFAULT_COLLATE_NAME"
  - "m_szCollateSchema"
  - "FORM_OF_USE"
  - "DEFAULT_COLLATE_SCHEMA"
  - "m_szCollateCatalog"
  - "CCharacterSets"
  - "CHARACTER_SET_NAME"
  - "DEFAULT_COLLATE_CATALOG"
  - "CHARACTER_SET_SCHEMA"
  - "m_szFormOfUse"
  - "NUMBER_OF_CHARACTERS"
  - "m_szSchema"
  - "CHARACTER_SET_CATALOG"
  - "CCharacterSetInfo"
  - "m_nNumCharacters"
  - "m_szName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCharacterSetInfo 매개 변수 클래스"
  - "CCharacterSets typedef 클래스"
  - "CHARACTER_SET_CATALOG"
  - "CHARACTER_SET_NAME"
  - "CHARACTER_SET_SCHEMA"
  - "DEFAULT_COLLATE_CATALOG"
  - "DEFAULT_COLLATE_NAME"
  - "DEFAULT_COLLATE_SCHEMA"
  - "FORM_OF_USE OLE DB 열"
  - "m_nNumCharacters"
  - "m_szCatalog"
  - "m_szCollateCatalog"
  - "m_szCollateName"
  - "m_szCollateSchema"
  - "m_szFormOfUse"
  - "m_szName"
  - "m_szSchema"
  - "NUMBER_OF_CHARACTERS"
ms.assetid: 029d068c-8bb2-4fc0-8709-78ce7f74446e
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CCharacterSets, CCharacterSetInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typedef 클래스를 호출**CCharacterSets** 매개 변수 클래스를 구현 하려면  **CCharacterSetInfo**에 호출합니다.  
  
## 설명  
 typedef 클래스를 사용하는 것에 대한 자세한 내용은 [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)를 참조하십시오.  
  
 이 클래스는 지정된 사용자가 액세스할 수 있는 카탈로그에 정의된 문자 변환을 식별합니다.  
  
 다음 표는 클래스 데이터 멤버 및 그들의 해당 OLE DB 열을 열거합니다.  스키마와 열에 대한 자세한 정보에 대하여, *OLE DB Programmer's Reference* 에서 [FOREIGN\_SETS Rowset](https://msdn.microsoft.com/en-us/library/ms722638.aspx)를 참고하세요.  
  
|데이터 멤버|OLE DB 열|  
|------------|--------------|  
|m\_szCatalog|CHARACTER\_SET\_CATALOG|  
|m\_szSchema|CHARACTER\_SET\_SCHEMA|  
|m\_szName|CHARACTER\_SET\_NAME|  
|m\_szFormOfUse|FORM\_OF\_USE|  
|m\_nNumCharacters|NUMBER\_OF\_CHARACTERS|  
|m\_szCollateCatalog|DEFAULT\_COLLATE\_CATALOG|  
|m\_szCollateSchema|DEFAULT\_COLLATE\_SCHEMA|  
|m\_szCollateName|DEFAULT\_COLLATE\_NAME|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)