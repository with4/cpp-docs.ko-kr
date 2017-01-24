---
title: "CDaoDatabaseInfo 구조체 | Microsoft Docs"
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
  - "CDaoDatabaseInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabaseInfo 구조체"
  - "DAO(Data Access Objects), 데이터베이스 데이터 정렬"
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoDatabaseInfo 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `CDaoDatabaseInfo` structure contains information about a database object defined for data access objects \(DAO\).  
  
## 구문  
  
```  
  
      struct CDaoDatabaseInfo  
{  
   CString m_strName;       // Primary  
   BOOL m_bUpdatable;       // Primary  
   BOOL m_bTransactions;    // Primary  
   CString m_strVersion;    // Secondary  
   long m_lCollatingOrder;  // Secondary  
   short m_nQueryTimeout;   // Secondary  
   CString m_strConnect;    // All  
};  
```  
  
#### 매개 변수  
 `m_strName`  
 Uniquely names the database object.  To directly retrieve this property, call [CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md).  For details, see the topic "Name Property" in DAO Help.  
  
 `m_bUpdatable`  
 Indicates whether changes can be made to the database.  To directly retrieve this property, call [CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md).  For details, see the topic "Updatable Property" in DAO Help.  
  
 *m\_bTransactions*  
 Indicates whether a data source supports transactions — the recording of a series of changes that can later be rolled back \(canceled\) or committed \(saved\).  If a database is based on the Microsoft Jet database engine, the Transactions property is nonzero and you can use transactions.  Other database engines may not support transactions.  To directly retrieve this property, call [CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md).  For details, see the topic "Transactions Property" in DAO Help.  
  
 *m\_strVersion*  
 Indicates the version of the Microsoft Jet database engine.  To retrieve the value of this property directly, call the database object's [GetVersion](../Topic/CDaoDatabase::GetVersion.md) member function.  For details, see the topic "Version Property" in DAO Help.  
  
 `m_lCollatingOrder`  
 Specifies the sequence of the sort order in text for string comparison or sorting.  가능한 값은 다음과 같습니다.  
  
-   **dbSortGeneral** Use the General \(English, French, German, Portuguese, Italian, and Modern Spanish\) sort order.  
  
-   **dbSortArabic** Use the Arabic sort order.  
  
-   **dbSortCyrillic** Use the Russian sort order.  
  
-   **dbSortCzech** Use the Czech sort order.  
  
-   **dbSortDutch** Use the Dutch sort order.  
  
-   **dbSortGreek** Use the Greek sort order.  
  
-   **dbSortHebrew** Use the Hebrew sort order.  
  
-   **dbSortHungarian** Use the Hungarian sort order.  
  
-   **dbSortIcelandic** Use the Icelandic sort order.  
  
-   **dbSortNorwdan** Use the Norwegian or Danish sort order.  
  
-   **dbSortPDXIntl** Use the Paradox International sort order.  
  
-   **dbSortPDXNor** Use the Paradox Norwegian or Danish sort order.  
  
-   **dbSortPDXSwe** Use the Paradox Swedish or Finnish sort order.  
  
-   **dbSortPolish** Use the Polish sort order.  
  
-   **dbSortSpanish** Use the Spanish sort order.  
  
-   **dbSortSwedFin** Use the Swedish or Finnish sort order.  
  
-   **dbSortTurkish** Use the Turkish sort order.  
  
-   **dbSortUndefined** The sort order is undefined or unknown.  
  
 For more information, see the topic "Customizing Windows Registry Settings for Data Access" in DAO Help.  
  
 *m\_nQueryTimeout*  
 The number of seconds the Microsoft Jet database engine waits before a timeout error occurs when a query is run on an ODBC database.  The default timeout value is 60 seconds.  When QueryTimeout is set to 0, no timeout occurs; this can cause the program to stop responding.  To retrieve the value of this property directly, call the database object's [GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md) member function.  For details, see the topic "QueryTimeout Property" in DAO Help.  
  
 `m_strConnect`  
 Provides information about the source of an open database.  For information about connect strings, and for information about retrieving the value of this property directly, see the [CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md) member function.  For more information, see the topic "Connect Property" in DAO Help.  
  
## 설명  
 The database is a DAO object underlying an MFC object of class [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md).  The references to Primary, Secondary, and All above indicate how the information is returned by the [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) member function.  
  
 Information retrieved by the [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) member function is stored in a `CDaoDatabaseInfo` structure.  Call `GetDatabaseInfo` for the `CDaoWorkspace` object in whose Databases collection the database object is stored.  `CDaoDatabaseInfo` also defines a `Dump` member function in debug builds.  You can use `Dump` to dump the contents of a `CDaoDatabaseInfo` object.  
  
## 요구 사항  
 **Header:** afxdao.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)