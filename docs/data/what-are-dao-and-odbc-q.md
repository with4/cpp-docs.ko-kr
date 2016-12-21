---
title: "DAO와 ODBC란 무엇입니까? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO(Data Access Objects), 및 ODBC"
  - "ODBC, ODBC 정보"
ms.assetid: 22cc2f75-7ff6-47bc-ac56-56a40591104c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO와 ODBC란 무엇입니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DAO\(Data Access Object\)와 ODBC\(Open Database Connectivity\)는 둘 다 특정 데이터베이스 관리 시스템\(DBMS\)과 독립적인 응용 프로그램을 작성할 수 있는 기능을 제공하는 API입니다.  
  
 DAO는 Microsoft Access Basic이나 Microsoft Visual Basic을 사용하는 데이터베이스 프로그래머에게 친숙한 인터페이스입니다.  DAO는 Microsoft Jet 데이터베이스 엔진을 사용하여 데이터 액세스 개체 집합, 데이터베이스 개체, tabledef와 querydef 개체 및 레코드 집합 개체 등을 제공합니다.  DAO는 Microsoft Access에서 만든 .mdb 파일에 가장 적합하지만 DAO와 Microsoft Jet 데이터베이스 엔진을 통해서도 ODBC 데이터 원본에 액세스할 수 있습니다.  
  
 ODBC는 다른 데이터베이스 공급업체가 특정 DBMS와 관련된 ODBC 드라이버를 통해 구현하는 API를 제공합니다.  사용자가 만든 프로그램은 이 API를 사용하여 ODBC 드라이버 관리자를 호출하며, 적절한 드라이버로 호출을 전달합니다.  그러면 이 드라이버가 SQL을 사용하여 DBMS와 상호 작용합니다.  
  
> [!NOTE]
>  ODBC는 Microsoft WOSA\(Windows Open Standards Architecture\)의 주요 부분입니다.  DAO는 Microsoft Jet 데이터베이스 엔진에 맞게 최적화되었지만 이 엔진을 사용하여 ODBC와 기타 외부 데이터 소스에 액세스할 수 있고, 이 엔진에 바탕을 둔 별도의 ODBC API와 MFC 클래스를 사용할 수 있으며, 사용자가 데이터베이스 도구를 선택할 때도 각각의 역할을 수행합니다.  
  
## 참고 항목  
 [데이터 액세스에 대한 질문과 대답](../data/data-access-frequently-asked-questions-mfc-data-access.md)