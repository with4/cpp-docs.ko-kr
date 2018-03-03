---
title: "ODBC 기초 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26a1554fec567762810f6bd48c8674ea048ce117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-basics"></a>ODBC 기초
이 항목의 ODBC Open Database Connectivity () 기본 사항을 제공합니다.  
  
-   [ODBC는 데이터베이스 클래스와 함께 작동 하는 방법](../../data/odbc/odbc-and-the-database-classes.md)  
  
-   [ODBC 드라이버 다이너셋와 작동 하는 방법](../../data/odbc/odbc-driver-requirements-for-dynasets.md)  
  
-   [ODBC 구성 요소 응용 프로그램과 함께 재배포할 필요](../../data/odbc/redistributing-odbc-components-to-your-customers.md)  
  
 관련된 항목을 읽으려면 보려는 경우도 있습니다 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.  
  
> [!NOTE]
>  ODBC 데이터 소스는이 항목에 설명 된 대로 MFC ODBC 클래스를 통해 또는 MFC 데이터 액세스 개체 (DAO) 클래스를 통해 액세스할 수 있습니다.  
  
> [!NOTE]
>  MFC ODBC 클래스에는 유니코드 지원 및 다중 스레딩 합니다. 다중 스레딩 지원에 대 한 자세한 내용은 참조 [ODBC 클래스와 스레드](../../data/odbc/odbc-classes-and-threads.md)  
  
 ODBC는 응용 프로그램이 ODBC 드라이버는 모든 데이터베이스 데이터에에서 액세스할 수 있도록 하는 호출 수준 인터페이스입니다. ODBC를 사용 하면 최종 사용자가 ODBC 드라이버가 있는 모든 데이터베이스에 액세스할 수 있는 데이터베이스 응용 프로그램을 만들 수 있습니다. ODBC 응용 프로그램을 원본 데이터베이스 관리 시스템 (DBMS)에 대해 독립적일 수 있는 API를 제공 합니다.  
  
 ODBC는 Windows 기반 데스크톱 응용 프로그램을 각 플랫폼에 대 한 응용 프로그램을 다시 작성 하지 않고 여러 컴퓨팅 환경에 연결 하는 데 인터페이스인의 Microsoft Windows 열기 서비스 아키텍처 (WOSA), 데이터베이스 부분입니다.  
  
 다음은 ODBC의 구성 요소입니다.  
  
-   ODBC API  
  
     다양 한 오류 코드 및 표준 라이브러리 함수를 호출 [SQL](../../data/odbc/sql.md) Dbms의 데이터에 액세스 하기 위한 구문이 있습니다.  
  
-   ODBC 드라이버 관리자  
  
     동적 연결 라이브러리 (Odbc32.dll) 응용 프로그램 대신 ODBC 데이터베이스 드라이버를 로드 하 합니다. 응용 프로그램에 투명 합니다.  
  
-   ODBC 데이터베이스 드라이버  
  
     특정 Dbms에 대 한 ODBC 함수 호출을 처리 하는 하나 이상의 Dll 제공 된 드라이버의 목록이 참조 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.  
  
-   [ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
     동적 연결 라이브러리 (Odbccr32.dll) 드라이버 및 ODBC 드라이버 관리자 사이 하 고 스크롤 하는 데이터를 처리 하는입니다.  
  
-   [ODBC 관리자](../../data/odbc/odbc-administrator.md)  
  
     응용 프로그램에 대 한 데이터 원본으로 사용할 수 있도록 DBMS를 구성 하는 데 사용 되는 도구입니다.  
  
 응용 프로그램을 만들려면 Dbms에서 DBMS에 직접 작업 하지 않고 DBMS 특별히 작성 된 ODBC 드라이버를 통해 작업 합니다. 드라이버는 DBMS צ ְ ײ, 개발자의 작업을 단순화 하 고 다양 한 데이터 소스를 사용할 수 있도록 명령으로 호출으로 변환 합니다.  
  
 데이터베이스 클래스는 ODBC 드라이버는 권한이 있는 모든 데이터 소스를 지원 합니다. 여기에서 예를 들어, 관계형 데이터베이스, 인덱싱된 순차적 액세스 메서드 (ISAM) 데이터베이스, Microsoft Excel 스프레드시트 또는 텍스트 파일에 포함 됩니다. ODBC 드라이버로 데이터 원본에 대 한 연결을 관리 하 고 SQL을 사용 하 여 데이터베이스에서 레코드를 선택 합니다.  
  
 이 버전의 Visual c + +에 포함 된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대 한 정보에 대 한 참조 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)