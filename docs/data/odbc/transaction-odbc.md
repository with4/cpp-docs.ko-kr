---
title: "트랜잭션(ODBC) | Microsoft Docs"
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
  - "데이터베이스[C++], 트랜잭션"
  - "ODBC[C++], 트랜잭션"
  - "ODBC 레코드 집합[C++], 트랜잭션"
  - "ODBC 레코드 집합[C++], 업데이트"
  - "레코드 집합[C++], 트랜잭션"
  - "레코드 집합[C++], 업데이트"
  - "트랜잭션[C++], MFC ODBC 클래스"
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 트랜잭션(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 트랜잭션은 [데이터 소스](../../data/odbc/data-source-odbc.md) 업데이트를 그룹화하거나 일괄 처리하여 모든 변경 내용을 한 번에 커밋하거나 해당 트랜잭션을 롤백하는 경우 어떠한 변경 내용도 커밋되지 않도록 하는 방법입니다.  트랜잭션을 사용하지 않는 경우 데이터 소스의 변경 내용은 필요할 때 커밋되는 대신 자동으로 커밋됩니다.  
  
> [!NOTE]
>  모든 ODBC 데이터베이스 드라이버가 트랜잭션을 지원하지는 않습니다.  지정한 데이터베이스에 대해 드라이버가 트랜잭션을 지원하는지 여부를 확인하려면 [CDatabase](../../mfc/reference/cdatabase-class.md)나 [CRecordset](../../mfc/reference/crecordset-class.md) 개체의 `CanTransact` 멤버 함수를 호출합니다.  `CanTransact`는 데이터 소스가 트랜잭션을 전적으로 지원하는지 여부를 알려주지는 않습니다.  열려 있는 `CRecordset` 개체에 대한 트랜잭션의 효과를 확인하려면 **CommitTrans**와 **Rollback**을 호출한 다음 `CDatabase::GetCursorCommitBehavior`와 `CDatabase::GetCursorRollbackBehavior`도 호출해야 합니다.  
  
 `CRecordset` 개체의 `AddNew`와 **Edit** 멤버 함수를 호출하면 **Update**를 호출할 때 데이터 소스에 즉시 영향을 줍니다.  **Delete** 호출도 이와 동일합니다.  반면에 `AddNew`, **Edit**, **Update** 및 **Delete**에 대한 다중 호출로 구성된 트랜잭션을 사용할 수 있습니다. 이 트랜잭션은 **CommitTrans**를 명시적으로 호출하기 전까지는 수행은 되지만 커밋되지는 않습니다.  또한 트랜잭션 설정을 통해 롤백 기능을 유지하면서 호출을 실행할 수 있습니다.  중요한 리소스를 사용할 수 없거나 기타 상황으로 인해 전체 트랜잭션을 완료할 수 없는 경우 트랜잭션을 커밋하는 대신 롤백할 수 있습니다.  이 경우에는 트랜잭션의 어떠한 변경 내용도 데이터 소스에 적용되지 않습니다.  
  
> [!NOTE]
>  `CRecordset` 클래스는 대량 행 페치를 구현한 경우 데이터 소스의 업데이트를 지원하지 않습니다.  즉 `AddNew`, **Edit**, **Delete** 또는 **Update**를 호출할 수 없습니다.  그러나 업데이트를 수행할 함수를 직접 작성한 다음 지정한 트랜잭션에서 해당 함수를 호출할 수 있습니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
> [!NOTE]
>  트랜잭션은 레코드 집합에 영향을 줄 뿐만 아니라 `CDatabase` 개체와 관련된 ODBC **HDBC**나 이 **HDBC**를 기반으로 하는 ODBC **HSTMT**를 사용하는 경우 직접 실행하는SQL 문에도 영향을 줍니다.  
  
 특히 트랜잭션은 동시에 업데이트해야 하는 여러 레코드를 가지고 있을 때 유용합니다.  이러한 경우 최종 업데이트가 완료되기 전에 예외가 throw되어 트랜잭션이 완료되지 못할 수 있습니다.  이와 같은 업데이트를 한 개의 트랜잭션으로 그룹화하면 변경 내용을 복구\(롤백\)하고 레코드를 트랜잭션 이전의 상태로 반환할 수 있습니다.  예를 들어, 은행에서 A 계좌로부터 B 계좌로 송금하는 업무를 정확히 처리하려면 A 계좌에서 출금하고 B 계좌로 입금하는 작업이 모두 성공해야 하며 그렇지 않은 경우 전체 트랜잭션이 실패되어야 합니다.  
  
 데이터베이스 클래스에서 `CDatabase` 개체를 통해 트랜잭션을 수행합니다.  `CDatabase` 개체는 데이터 소스와의 연결을 나타내며 `CDatabase` 개체와 관련된 한 개 이상의 레코드 집합이 레코드 집합 멤버 함수를 통해 데이터베이스의 테이블에서 실행됩니다.  
  
> [!NOTE]
>  한 수준의 트랜잭션만 지원됩니다.  트랜잭션을 중첩하거나 여러 데이터베이스 개체로 확장할 수 없습니다.  
  
 트랜잭션을 수행하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [트랜잭션: 레코드 집합에서 트랜잭션 수행\(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [트랜잭션: 트랜잭션이 업데이트에 미치는 영향\(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)