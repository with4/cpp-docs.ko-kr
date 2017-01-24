---
title: "DAO와 ODBC를 사용하여 액세스할 수 있는 데이터 소스는 무엇입니까? | Microsoft Docs"
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
  - "DAO[C++], 데이터 소스 형식"
  - "데이터[C++], DAO"
  - "데이터[C++], ODBC"
  - "데이터 액세스[C++], DAO"
  - "데이터 소스[C++], DAO 및 ODBC를 사용하여 액세스 가능"
  - "데이터베이스[C++], DAO에서 액세스"
  - "FAQ[C++], 액세스 가능한 데이터베이스"
  - "ODBC[C++], 액세스 가능한 데이터 소스"
  - "ODBC 데이터 소스[C++], 액세스 가능"
ms.assetid: c88abb45-526a-467a-a01b-d9396bd63236
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO와 ODBC를 사용하여 액세스할 수 있는 데이터 소스는 무엇입니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 MFC 클래스 집합을 사용하여 다양한 데이터 소스에 액세스할 수 있고 데이터 소스와 독립된 응용 프로그램을 작성할 수 있습니다.  
  
##  <a name="_core_databases_you_can_access_with_dao"></a> DAO를 사용하여 액세스할 수 있는 데이터베이스  
 DAO와 MFC DAO 클래스를 사용하여 액세스할 수 있는 데이터 소스는 다음과 같습니다.  
  
-   Microsoft Jet 데이터베이스 엔진을 사용하고, Microsoft Access나 Microsoft Visual Basic 데이터베이스 엔진 1.x, 2.x 및 3.0으로 만든 데이터베이스  
  
-   설치할 수 있는 ISAM 데이터베이스는 다음과 같습니다.  
  
    -   dBASE III, dBASE IV 및 dBASE 5.0  
  
    -   Paradox 3.x, 4.x 및 5.x  
  
-   ODBC\(Open Database Connectivity\) 데이터베이스\(Microsoft SQL Server, SYBASE SQL Server 및 ORACLE Server 포함\).  ODBC 데이터베이스에 액세스하려면 액세스할 데이터베이스에 사용할 적절한 ODBC 드라이버가 있어야 합니다.  이 버전의 Visual C\+\+에 포함된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대한 내용은 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
-   Microsoft Excel 3.0, 4.0, 5.0 및 7.0 워크시트  
  
-   Lotus WKS, WK1, WK3 및 WK4 스프레드시트  
  
-   텍스트 파일  
  
 DAO는 ODBC 데이터 소스를 제외한 위의 모든 항목을 포함하여 Microsoft Jet 데이터베이스 엔진에서 읽을 수 있는 데이터베이스와 함께 사용하는 것이 좋습니다.  Microsoft Jet\(.mdb\) 데이터베이스에 사용할 때 최적의 성능을 내고,  특히 ODBC 데이터 원본에 있는 외부 테이블을 .mdb 데이터베이스에 연결하면 연결하지 않고 MFC DAO 클래스를 통해 직접 외부 데이터베이스를 열 때보다 효율적입니다.  
  
##  <a name="_core_databases_you_can_access_with_odbc"></a> ODBC를 사용하여 액세스할 수 있는 데이터베이스  
 ODBC와 MFC ODBC 클래스를 사용할 경우 응용 프로그램 사용자에게 적절한 ODBC 드라이버가 있으면 로컬과 원격에 있는 모든 데이터 소스에 액세스할 수 있습니다. 다양한 데이터 소스에 16비트, 32비트 및 64비트 ODBC 드라이버를 사용할 수 있습니다.  Microsoft Jet\(.mdb\) 데이터베이스로 작업할 경우에는 Microsoft Access ODBC 드라이버보다 DAO 클래스를 사용하는 것이 보다 효율적입니다.  
  
## 참고 항목  
 [데이터 액세스에 대한 질문과 대답](../data/data-access-frequently-asked-questions-mfc-data-access.md)