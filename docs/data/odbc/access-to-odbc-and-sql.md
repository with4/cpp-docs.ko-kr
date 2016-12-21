---
title: "ODBC 및 SQL 액세스 | Microsoft Docs"
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
  - "API 호출[C++], 직접 DAO 또는 ODBC 호출"
  - "ODBC[C++], API 함수"
  - "ODBC API 함수[C++]"
  - "ODBC API 함수[C++], MFC에서 호출"
  - "SQL[C++], ODBC API 함수 호출"
  - "Windows API[C++], MFC에서 호출"
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC 및 SQL 액세스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 라이브러리에는 많은 Windows API 함수가 캡슐화되어 있으며 프로그래머가 Windows API 함수를 직접 호출할 수도 있습니다.  데이터베이스 클래스는 ODBC API와 비교할 때 동일한 유연성을 제공합니다.  데이터베이스 클래스를 이용하면 ODBC 사용과 관련된 복잡한 문제를 피할 수 있는 반면 프로그램의 어디서나 ODBC API 함수를 직접 호출할 수도 있습니다.  
  
 마찬가지로 데이터베이스 클래스를 이용하면 좀더 쉽게 [SQL](../../data/odbc/sql.md) 작업을 수행할 수 있지만 필요하면 SQL을 직접 사용할 수도 있습니다.  레코드 집합을 열 때 사용자 지정 SQL 문 또는 기본 명령문의 설정 부분을 전달하여 레코드 집합 개체를 사용자 지정할 수 있습니다.  또한 [CDatabase](../../mfc/reference/cdatabase-class.md) 클래스의 [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) 멤버 함수를 사용하여 SQL을 직접 호출할 수도 있습니다.  
  
 자세한 내용은 [ODBC: ODBC API 함수 직접 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) 및 [SQL: SQL 직접 호출\(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)