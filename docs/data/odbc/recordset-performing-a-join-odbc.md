---
title: "레코드 집합: 조인 수행(ODBC) | Microsoft Docs"
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
  - "데이터 바인딩[C++], 레코드 집합의 열"
  - "데이터 바인딩[C++], 레코드 집합 열"
  - "필터[C++], 레코드 집합에 대한 조인 조건"
  - "조인[C++], 레코드 집합"
  - "ODBC 레코드 집합[C++], 조인"
  - "레코드 집합[C++], 데이터 바인딩"
  - "레코드 집합[C++], 테이블 조인"
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 조인 수행(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
## 조인의 정의  
 공용 데이터 액세스 연산인 조인 연산을 통해 단일 레코드 집합 개체를 사용하는 여러 테이블에 있는 데이터를 사용하여 작업할 수 있습니다.  두 개 이상의 테이블을 조인하면 레코드 집합에는 각 테이블의 열이 포함되지만 응용 프로그램에는 단일 테이블처럼 나타납니다.  조인에서 모든 테이블의 모든 열을 사용하는 경우도 있지만 조인 연산의 SQL **SELECT** 절을 통해 각 테이블의 일부 열만을 사용하기도 합니다.  데이터베이스 클래스는 읽기 전용 조인을 지원하지만 업데이트 가능한 조인은 지원하지 않습니다.  
  
 조인된 테이블의 열이 포함된 레코드를 선택하려면 다음 항목이 필요합니다.  
  
-   조인된 모든 테이블의 이름을 포함하는 테이블 목록  
  
-   조인 연산과 관련된 모든 열의 이름이 포함되는 열 목록.  이름은 같지만 서로 다른 테이블에 있는 열은 테이블 이름에 의해 구분됩니다.  
  
-   테이블 조인에 사용되는 열을 지정하는 필터\(SQL **WHERE** 절\).  이 필터는 "Table1.KeyCol \= Table2.KeyCol"의 형식이며 실제로 조인을 수행합니다.  
  
 같은 방법으로 SQL 키워드 **AND**로 조인된 여러 쌍의 열을 연결하여 두 개 이상의 테이블을 조인할 수 있습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 미리 정의된 쿼리에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [레코드 집합: 테이블에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [레코드 집합: 레코드 집합 다시 쿼리\(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)