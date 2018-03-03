---
title: "트랜잭션 (ODBC) | Microsoft Docs"
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
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2816e1cfe3c62fecede5c909bc1593779aa90d54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="transaction-odbc"></a>트랜잭션(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 그룹화 또는 일괄 처리 하는 일련의에 대 한 업데이트 방법는 [데이터 소스](../../data/odbc/data-source-odbc.md) 한 번에 커밋된 모두 또는 트랜잭션을 롤백하는 경우 커밋되지 않으며 되도록 합니다. 트랜잭션을 사용 하지 않는 경우 데이터 원본의 변경 내용이 필요할 때 커밋되는 대신 자동으로 커밋됩니다.  
  
> [!NOTE]
>  일부 ODBC 데이터베이스 드라이버는 트랜잭션을 지원 합니다. 호출의 `CanTransact` 멤버 함수는 프로그램 [CDatabase](../../mfc/reference/cdatabase-class.md) 또는 [CRecordset](../../mfc/reference/crecordset-class.md) 드라이버에 지정된 된 데이터베이스에 대 한 트랜잭션을 지원 하는지 여부를 결정 하는 개체입니다. `CanTransact` 알려주지 않습니다 데이터 소스를 전체 트랜잭션 지원을 제공 하는지 여부입니다. 도 호출 해야 `CDatabase::GetCursorCommitBehavior` 및 `CDatabase::GetCursorRollbackBehavior` 후 **CommitTrans** 및 **롤백** 열기에 트랜잭션 효과 확인 하려면 `CRecordset` 개체입니다.  
  
 에 대 한 호출이 `AddNew` 및 **편집** 의 멤버 함수는 `CRecordset` 즉시 호출 하는 경우 데이터 원본에 영향을 줍니다. 개체 **업데이트**합니다. **삭제** 호출 또한 즉시 적용 합니다. 반면,를 여러 번 호출으로 구성 된 트랜잭션을 사용할 수 있습니다 `AddNew`, **편집**, **업데이트**, 및 **삭제**까지 커밋되지 않은 수행 되는 호출 하면 **CommitTrans** 명시적으로 합니다. 트랜잭션을 설정 하 여 롤백 수 있는 기능을 유지 하면서 일련의 이러한 호출을 실행할 수 있습니다. 중요 한 리소스를 사용할 수 없거나 일부 다른 상태로 완료 되 고 전체 트랜잭션을 방지 하는 경우 롤백할 수 있습니다 트랜잭션을 커밋하는 대신 합니다. 이 경우 데이터 원본에 영향을 트랜잭션이에 속하는 변경 합니다.  
  
> [!NOTE]
>  현재 클래스 `CRecordset` 대량 행 페치를 구현한 경우 데이터 원본에 대 한 업데이트를 지원 하지 않습니다. 즉, 호출을 만들 수 없습니다 `AddNew`, **편집**, **삭제**, 또는 **업데이트**합니다. 그러나 다음 지정된 된 트랜잭션 내에서 이러한 함수를 호출 하 고 업데이트를 수행 하려면 함수를 직접 있습니다 것을 작성할 수 있습니다. 대량 행 페치에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
> [!NOTE]
>  레코드 집합에 영향을 주는 것 외에도 트랜잭션이 주는 영향으로 ODBC를 사용 하 여 직접 실행 하는 SQL 문의 **HDBC** 와 연결 된 프로그램 `CDatabase` 개체 또는 ODBC **HSTMT** 기반 **HDBC**합니다.  
  
 트랜잭션은 동시에 업데이트 해야 하는 여러 레코드가 있는 경우 특히 유용 합니다. 이 경우 않으려면는 완료 트랜잭션이 마지막으로 업데이트 하려고 하기 전에 예외가 throw 된 경우에 발생할 수 있습니다. 이러한 업데이트는 트랜잭션으로 그룹화 변경 내용 으로부터 복구 (롤백) 하 고 트랜잭션 이전의 상태로 레코드를 반환 합니다. 예를 들어 은행 계정 A에서에서 B 계좌로 돈을 이체, 하는 경우 모두 B로 A, 입금 로부터의 출금 해야 성공는 송금이 정상적으로 처리 하거나 전체 거래가 실패 해야 합니다.  
  
 데이터베이스 클래스를 통해 트랜잭션을 수행 `CDatabase` 개체입니다. A `CDatabase` 개체 데이터 소스에 대 한 연결을 나타내며 하나 이상의 레코드 집합의 레코드와 연결 된 `CDatabase` 레코드 집합 멤버 함수를 통해 데이터베이스의 테이블에서 개체를 실행 합니다.  
  
> [!NOTE]
>  트랜잭션 수준이 하나만 지원 됩니다. 트랜잭션을 중첩할 수 없습니다 또는 여러 데이터베이스 개체가 확장할 수 있습니다.  
  
 다음 항목에서는 트랜잭션을 수행 하는 방법에 대 한 자세한 정보가 표시 됩니다.  
  
-   [트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## <a name="see-also"></a>참고 항목  
 [ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)