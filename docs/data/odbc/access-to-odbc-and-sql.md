---
title: ODBC 및 SQL 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4fb5daa988614e7e9cb058fce183c6af5b50dd30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="access-to-odbc-and-sql"></a>ODBC 및 SQL 액세스
Microsoft Foundation Class 라이브러리는 많은 Windows API 호출을 캡슐화 하 고 여전히 모든 Windows API 함수를 직접 호출할 수 있습니다. 데이터베이스 클래스는 ODBC API를 고려 하 여 동일한 유연성을 제공 합니다. 데이터베이스 클래스는 하면 ODBC의 복잡성을 보호 하는 동안 모든 위치에서 직접 ODBC API 함수를 호출할 수 있습니다 프로그램에 있습니다.  
  
 마찬가지로, 데이터베이스 클래스를 이용 하면 좀더 작업 하는 것과 [SQL](../../data/odbc/sql.md), 하지만 원하는 경우 SQL을 직접 사용할 수 있습니다. 사용자 지정 SQL 문 (또는 기본 문의 설정 부분)를 전달 하 여 recordset 개체를 사용자 지정할 수는 레코드 집합을 열 때입니다. SQL 호출을 사용 하 여 직접 만들 수도 있습니다는 [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) 클래스의 멤버 함수 [CDatabase](../../mfc/reference/cdatabase-class.md)합니다.  
  
 자세한 내용은 참조 [ODBC: 호출 ODBC API 함수 직접](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) 및 [SQL: 만드는 직접 SQL 호출 (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)