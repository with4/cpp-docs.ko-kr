---
title: 데이터 원본에 연결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b6a33f1e2421c56f89184d26185903b4ec7859e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088393"
---
# <a name="connecting-to-a-data-source"></a>데이터 소스에 연결
ODBC 데이터 소스는 특정 집합의 데이터를 해당 데이터와 데이터 소스 이름을 사용 하 여 표시할 수 있는 데이터 원본의 위치에 액세스 하는 데 필요한 정보입니다. 프로그램의 관점에서 데이터 원본에는 데이터, DBMS, 네트워크 (있는 경우) 및 ODBC 포함 됩니다.  
  
 데이터 원본에서 제공 하는 데이터에 액세스 하려면 프로그램 데이터 원본에 대 한 연결을 먼저 설정 해야 합니다. 모든 데이터 액세스는 해당 연결을 통해 관리 됩니다.  
  
 데이터 소스 연결 클래스에 의해 캡슐화 됩니다 [CDatabase](../../mfc/reference/cdatabase-class.md)합니다. 경우는 `CDatabase` 개체가 데이터 원본에 연결 된, 수행할 수 있습니다.  
  
-   생성 [레코드 집합](../../mfc/reference/crecordset-class.md), 테이블 또는 쿼리에서 레코드를 선택 합니다.  
  
-   관리 [트랜잭션을](../../data/odbc/transaction-odbc.md), 모든 일괄 처리 업데이트를 한 번에 데이터 소스에 커밋되는 (또는 전체 트랜잭션이 데이터 소스 변경 되지 않습니다. 다시 돌리거나)-데이터 원본에서 트랜잭션이 필요한 수준의 지원 합니다.  
  
-   직접 실행 [SQL](../../data/odbc/sql.md) 문.  
  
 데이터 원본에 연결 된 작업을 완료 하면 닫으면는 `CDatabase` 개체와 삭제 하거나 새 연결에 다시 사용 합니다. 데이터 원본 연결에 대 한 자세한 내용은 참조 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)