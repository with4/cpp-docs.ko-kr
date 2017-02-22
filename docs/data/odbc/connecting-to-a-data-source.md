---
title: "데이터 소스에 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연결[C++], 데이터 소스"
  - "데이터 소스[C++], 연결"
  - "데이터베이스 연결[C++], MFC ODBC 클래스"
  - "데이터베이스 연결[C++], ODBC"
  - "데이터베이스[C++], 연결"
  - "ODBC 연결[C++], using"
  - "ODBC 데이터 소스[C++], 연결"
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 데이터 소스에 연결
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC 데이터 소스는 데이터, 데이터에 액세스하는 데 필요한 정보, 데이터 소스 이름으로 표시할 수 있는 데이터 소스 위치 등으로 구성된 특정 집합입니다.  프로그램의 관점에서 볼 때 데이터 소스에는 데이터, DBMS, 네트워크\(있는 경우\), ODBC 등이 포함됩니다.  
  
 데이터 소스가 제공하는 데이터에 액세스하려면 프로그램에서 먼저 데이터 소스로 연결을 설정해야 합니다.  이 연결을 통해 데이터에 대한 모든 액세스를 관리합니다.  
  
 데이터 소스 연결은 [CDatabase](../../mfc/reference/cdatabase-class.md) 클래스에 의해 캡슐화됩니다.  `CDatabase` 개체가 데이터 소스에 연결된 후 다음과 같은 작업을 수행할 수 있습니다.  
  
-   테이블이나 쿼리에서 레코드를 선택하는 [레코드 집합](../../mfc/reference/crecordset-class.md)을 생성합니다.  
  
-   [트랜잭션](../../data/odbc/transaction-odbc.md)을 관리합니다. 데이터 소스가 필요한 트랜잭션 수준을 지원하는 경우, 일괄 업데이트를 통해 모든 트랜잭션을 한 번에 데이터 소스에 커밋하거나 데이터 소스가 변경되지 않도록 전체 트랜잭션을 롤백합니다.  
  
-   Directly execute [SQL](../../data/odbc/sql.md) statements.  
  
 데이터 소스 연결의 사용을 마치면 `CDatabase` 개체를 닫고 삭제하거나 새 연결에 다시 사용합니다.  데이터 소스 연결에 대한 자세한 내용은 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md)를 참조하십시오.  
  
## 참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)