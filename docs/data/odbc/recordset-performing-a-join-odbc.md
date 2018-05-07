---
title: '레코드 집합: 조인 수행 (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0be740a57f5c455b971dd23575401c666bf0723c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-performing-a-join-odbc"></a>레코드 집합: 조인 수행(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
## <a name="what-a-join-is"></a>어떤 조인이  
 조인 연산을 사용 하는 일반적인 데이터 액세스 작업을 사용 하면 단일 레코드 집합 개체를 사용 하 여 둘 이상의 테이블의 데이터를 사용할 수 있습니다. 각 테이블의 열이 포함 되지만 단일 테이블에 응용 프로그램으로 표시 된 레코드 집합을 생성 두 개 이상의 테이블을 조인 합니다. 조인에 모든 테이블 이지만 경우에 따라 SQL의 모든 열을 사용 하는 경우에 따라 **선택** 조인 절에서 각 테이블 열 중 일부만 사용 합니다. 데이터베이스 클래스에는 읽기 전용 조인 하지만 불가능 조인을 지원합니다.  
  
 조인 된 테이블의에서 열을 포함 하는 레코드를 선택 하려면 다음 항목이 필요 합니다.  
  
-   조인 된 모든 테이블의 이름이 포함 된 테이블 목록입니다.  
  
-   참여 하는 모든 열 이름이 포함 된 열 목록입니다. 에 이름이 같지만 서로 다른 테이블의 열은 테이블 이름으로 한정 됩니다.  
  
-   필터 (SQL **여기서** 절)과 테이블이 조인 열을 지정 하는 합니다. 이 필터 형식은 "Table1.KeyCol Table2.KeyCol =" 실제로 조인을 수행 하 고 있습니다.  
  
 SQL 키워드로 조인 된 여러 쌍의 열을 연결 하 여 같은 방식으로 두 개 이상의 테이블을 조인할 수 있습니다 **AND**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [레코드 집합: 테이블 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [레코드 집합: 레코드 집합 다시 쿼리(ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)