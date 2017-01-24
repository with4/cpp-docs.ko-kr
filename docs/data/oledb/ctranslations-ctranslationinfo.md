---
title: "CTranslations, CTranslationInfo | Microsoft Docs"
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
  - "m_szCatalog"
  - "m_szSourceCatalog"
  - "m_szTargetSchema"
  - "m_szTargetCatalog"
  - "m_szTargetName"
  - "CTranslationInfo"
  - "m_szSourceName"
  - "m_szSchema"
  - "CTranslations"
  - "m_szName"
  - "m_szSourceSchema"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTranslationInfo 매개 변수 클래스"
  - "CTranslations typedef 클래스"
  - "m_szCatalog"
  - "m_szName"
  - "m_szSchema"
  - "m_szSourceCatalog"
  - "m_szSourceName"
  - "m_szSourceSchema"
  - "m_szTargetCatalog"
  - "m_szTargetName"
  - "m_szTargetSchema"
ms.assetid: 19a64828-2d4c-42a0-8bfb-b010e334a9b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTranslations, CTranslationInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이것의 매개변수 클래스 **CTranslationInfo**를 구현하려면 typedef 클래스 **CTranslations** 를 호출합니다.  
  
## 설명  
 typedef 클래스를 사용하는 것에 대한 자세한 내용은 [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)를 참조하십시오.  
  
 이 클래스는 지정된 사용자가 액세스할 수 있는 카탈로그에 정의된 문자 변환을 식별합니다.  
  
 다음 표는 클래스 데이터 멤버 및 그들의 해당 OLE DB 열을 열거합니다.  스키마와 열에 대한 자세한 정보에 대하여, *OLE DB Programmer's Reference* 에서 [TRANSLATIONS Rowset](https://msdn.microsoft.com/en-us/library/ms725365.aspx) 를 참고하세요.  
  
|데이터 멤버|OLE DB 열|  
|------------|--------------|  
|m\_szCatalog|TRANSLATION\_CATALOG|  
|m\_szSchema|TRANSLATION\_SCHEMA|  
|m\_szName|TRANSLATION\_NAME|  
|m\_szSourceCatalog|SOURCE\_CHARACTER\_SET\_CATALOG|  
|m\_szSourceSchema|SOURCE\_CHARACTER\_SET\_SCHEMA|  
|m\_szSourceName|SOURCE\_CHARACTER\_SET\_NAME|  
|m\_szTargetCatalog|TARGET\_CHARACTER\_SET\_CATALOG|  
|m\_szTargetSchema|TARGET\_CHARACTER\_SET\_SCHEMA|  
|m\_szTargetName|TARGET\_CHARACTER\_SET\_NAME|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CatDB](../../top/visual-cpp-samples.md)   
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)