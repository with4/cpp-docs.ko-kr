---
title: "DAO와 ODBC를 사용해야 합니까? | Microsoft Docs"
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
  - "DAO[C++], ODBC와 비교"
  - "데이터베이스 클래스[C++], DAO"
  - "데이터베이스 클래스[C++], ODBC"
  - "ODBC[C++], DAO와 비교"
ms.assetid: 9f67613f-0056-4ece-8c3a-9872e9563d57
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO와 ODBC를 사용해야 합니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Visual C\+\+ .NET에서는 포함된 DAO 클래스를 아직 사용할 수 있지만 Visual C\+\+ 환경 및 마법사가 더 이상 DAO를 지원하지 않습니다.  Microsoft는 새 프로젝트에 대해 OLE DB 템플릿이나 ODBC를 사용할 것을 권장합니다.  DAO는 기존 응용 프로그램을 유지 관리하는 데만 사용할 수 있습니다.  
  
 어떤 MFC 클래스 집합을 사용해야 합니까?  사용자의 요구에 따라 다릅니다.  
  
-   특히, MFC ODBC 클래스가 더 나은 성능을 제공하는 클라이언트\/서버 환경에서 ODBC 데이터 원본으로만 작업할 경우에는 ODBC 클래스를 사용하십시오.  
  
-   주로 Microsoft Jet 데이터베이스\(.mdb\)나 Microsoft Jet 데이터베이스 엔진이 직접 읽을 수 있는 다른 데이터베이스로 작업할 경우에는 DAO 클래스를 사용하십시오.  이에 대한 목록은 [DAO와 ODBC를 사용하여 액세스할 수 있는 데이터 소스는 무엇입니까?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)를 참조하십시오.  
  
-   Microsoft Jet 데이터베이스 엔진의 속도와 DAO 클래스가 제공하는 추가 기능을 사용하려면 DAO 클래스를 통해 ODBC 데이터 원본에 액세스하십시오.  
  
    > [!NOTE]
    >  DAO 클래스를 사용하려면 추가 하드 디스크 공간이 필요합니다.  
  
 DAO 클래스를 사용하면 다음과 같은 이점이 있습니다.  
  
-   특히 Microsoft Jet 데이터베이스\(.mdb\)를 사용할 경우 성능이 향상됩니다.  
  
-   ODBC 클래스, Microsoft Access Basic 및 Microsoft Visual Basic과 호환이 가능합니다.  
  
-   유효성 검사 규칙에 액세스합니다.  
  
-   테이블 간의 관계를 지정하는 기능이 있습니다.  
  
-   DML\(데이터 조작 언어\)과 함께 DDL\(데이터 정의 언어\)을 지원하는 보다 뛰어난 데이터 액세스 모델입니다.  자세한 내용은 [데이터베이스 정의 및 조작](../data/are-ddl-and-dml-supported-q.md)을 참조하십시오.  
  
 다음 표에서는 선택에 도움이 되도록 주요 차이점을 간략하게 보여 줍니다.  
  
### MFC DAO 및 ODBC 클래스 선택  
  
|작업|DAO 클래스를 선택한 경우|ODBC 클래스를 선택한 경우|  
|--------|---------------------|----------------------|  
|.MDB 파일 액세스|예|예|  
|ODBC 데이터 소스 액세스|예|예|  
|16비트에서 사용 가능|아니요|예|  
|32비트에서 사용 가능|예|예|  
|64비트에서 사용 가능|아니요|예|  
|데이터베이스 압축|예|아니요|  
|데이터베이스 엔진 지원|Microsoft Jet 데이터베이스 엔진|대상 DBMS|  
|DDL 지원|예|직접적인 ODBC 호출을 통해서만 지원|  
|DML 지원|예|예|  
|MFC 구현의 속성|DAO 핵심 함수의 "래퍼"|ODBC API의 "래퍼"가 아닌 단순화된 추상화|  
|최적화|.mdb 파일\(Microsoft Access\)|특히 클라이언트\/서버 환경에서 드라이버가 있는 모든 DBMS|  
|트랜잭션 지원|솔루션 당, ODBC 데이터, 데이터베이스 당|데이터베이스 당|  
  
 ODBC 드라이버의 기능은 아주 다양하다는 점을 염두에 두십시오.  자세한 내용은 ODBC *Programmer's Reference*와 현재 사용하고 있는 ODBC 드라이버의 도움말 파일을 참조하십시오.  
  
## 참고 항목  
 [데이터 액세스에 대한 질문과 대답](../data/data-access-frequently-asked-questions-mfc-data-access.md)