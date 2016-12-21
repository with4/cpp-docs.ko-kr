---
title: "ODBC 기초 | Microsoft Docs"
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
  - "ODBC 구성 요소"
  - "ODBC 구성 요소, 필수 구성 요소"
  - "ODBC 커서 라이브러리[ODBC], ODBC 구성 요소"
  - "ODBC, ODBC 정보"
  - "ODBC, 구성 요소"
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC 기초
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 ODBC\(Open Database Connectivity\)에 대한 기본 내용에 대해 설명합니다.  
  
-   [데이터베이스 클래스를 사용한 ODBC 작동 방법](../../data/odbc/odbc-and-the-database-classes.md)  
  
-   [다이너셋을 사용한 ODBC 드라이버 작동 방법](../../data/odbc/odbc-driver-requirements-for-dynasets.md)  
  
-   [응용 프로그램과 함께 재배포해야 할 ODBC 구성 요소](../../data/odbc/redistributing-odbc-components-to-your-customers.md)  
  
 관련 항목인 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)의 내용도 참조하십시오.  
  
> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC DAO\(데이터 액세스 개체\) 클래스를 통해서도 액세스할 수 있습니다.  
  
> [!NOTE]
>  MFC ODBC 클래스는 유니코드와 다중 스레딩을 지원합니다.  다중 스레딩 지원에 대한 자세한 내용은 [ODBC 클래스와 스레드](../../data/odbc/odbc-classes-and-threads.md)를 참조하십시오.  
  
 ODBC는 호출 수준 인터페이스로, 응용 프로그램은 이 인터페이스를 통해 ODBC 드라이버가 있는 모든 데이터베이스의 데이터에 액세스할 수 있습니다.  ODBC를 사용하면 최종 사용자가 적절한 ODBC 드라이버가 있는 모든 데이터베이스에 액세스할 수 있는 데이터베이스 응용 프로그램을 만들 수 있습니다.  ODBC에서 제공하는 API를 이용하면 소스 DBMS\(데이터베이스 관리 시스템\)에 종속되지 않는 응용 프로그램을 만들 수 있습니다.  
  
 ODBC는 Microsoft WOSA\(Windows Open Services Architecture\)의 데이터베이스 부분으로, 이 인터페이스를 이용하면 각 플랫폼에 대해 Windows 기반 데스크톱 응용 프로그램을 다시 작성하지 않아도 응용 프로그램을 다중 컴퓨팅 환경에 연결할 수 있습니다.  
  
 ODBC의 구성 요소는 다음과 같습니다.  
  
-   ODBC API  
  
     함수 호출, 오류 코드 집합, DBMS의 데이터에 액세스하기 위한 표준 [SQL](../../data/odbc/sql.md) 구문이 포함된 라이브러리입니다.  
  
-   ODBC 드라이버 관리자  
  
     해당 응용 프로그램에 대해 ODBC 데이터베이스 드라이버를 로드하는 DLL\(Odbc32.dll\)로,  응용 프로그램에 투명합니다.  
  
-   ODBC 데이터베이스 드라이버  
  
     특정 DBMS에 대해 ODBC 함수를 처리하는 하나 이상의 DLL입니다.  제공되는 드라이버 목록을 보려면 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
-   [ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
     ODBC 드라이버 관리자와 드라이버 사이에 위치하면서 데이터 스크롤을 처리하는 DLL\(Odbccr32.dll\)입니다.  
  
-   [ODBC 관리자](../../data/odbc/odbc-administrator.md)  
  
     DBMS를 응용 프로그램의 데이터 소스로 사용할 수 있도록 설정하는 도구입니다.  
  
 DBMS에 독립적인 응용 프로그램을 만들려면 직접 DBMS로 작업하기보다는 특정 DBMS용으로 작성된 ODBC 드라이버를 통해 작업을 수행하는 것이 좋습니다.  드라이버가 호출을 해당 DBMS가 사용할 수 있는 명령으로 변환하므로 개발자의 작업이 간편해지고 광범위한 데이터 소스에서 명령을 사용할 수 있습니다.  
  
 데이터베이스 클래스는 해당 ODBC 드라이버가 있는 모든 데이터 소스를 지원합니다.  이러한 데이터 소스의 예로 관계형 데이터베이스, ISAM\(Indexed Sequential Access Method\) 데이터베이스, Microsoft Excel 스프레드시트, 텍스트 파일 등이 있습니다.  ODBC 드라이버로 데이터 소스 연결을 관리하고 SQL을 사용하여 데이터베이스에서 레코드를 선택하면 됩니다.  
  
 이 버전의 Visual C\+\+에 포함된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대한 내용은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)