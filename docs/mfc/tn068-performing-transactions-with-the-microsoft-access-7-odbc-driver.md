---
title: "TN068: Microsoft Access 7 ODBC 드라이버를 사용 하 여 트랜잭션을 수행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.data.odbc
dev_langs: C++
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6db31d6301f2f0937d7bb5b83e77bf59936efdfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Microsoft Access 7 ODBC 드라이버를 사용하여 트랜잭션 수행
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트 MFC ODBC 데이터베이스 클래스와 Microsoft ODBC Desktop Driver Pack 버전 3.0에에서 포함 된 Microsoft Access 7.0 ODBC 드라이버를 사용 하는 경우 트랜잭션을 수행 하는 방법에 설명 합니다.  
  
## <a name="overview"></a>개요  
 호출 주의 해야 하는 경우 트랜잭션을 수행 하는 데이터베이스 응용 프로그램, `CDatabase::BeginTrans` 및 `CRecordset::Open` 응용 프로그램에서 올바른 순서로 합니다. Microsoft Jet 데이터베이스 엔진을 사용 하 여 Microsoft Access 7.0 드라이버 있으며 Jet 응용 프로그램에 하지 열린 커서가 있는 모든 데이터베이스에서 트랜잭션을 시작 합니다. MFC ODBC 데이터베이스 클래스에 대 한 열린 커서와 동일 열린 `CRecordset` 개체입니다.  
  
 호출 하기 전에 레코드 집합을 열 경우 **BeginTrans**, 모든 오류 메시지가 나타나지 않을 수 있습니다. 그러나 모든 레코드 집합 업데이트 사항이 호출한 후 영구적 프로그램 응용 프로그램을 사용 하면 `CRecordset::Update`, 업데이트는 롤백되지 다시 호출 하 여 및 **롤백**합니다. 이 문제를 방지 하려면 **BeginTrans** 첫 번째 레코드 집합을 엽니다.  
  
 MFC 커서 commit 및 rollback 동작에 대 한 드라이버 기능을 확인합니다. 클래스 `CDatabase` 두 멤버 함수를 제공 `GetCursorCommitBehavior` 및 `GetCursorRollbackBehavior`, 프로그램 열 트랜잭션 효과를 확인할 `CRecordset` 개체입니다. Microsoft Access 7.0 ODBC 드라이버에 대 한 이러한 멤버 함수는 다음과 같이 반환 됩니다. `SQL_CB_CLOSE` Access 드라이버 커서 유지 기능을 지원 하지 않으므로 합니다. 따라서 호출 해야 `CRecordset::Requery` 다음는 **CommitTrans** 또는 **롤백** 작업 합니다.  
  
 한 번에 하나씩 여러 트랜잭션을 수행 해야 할 경우 호출할 수 없습니다 **Requery** 첫 번째 트랜잭션이 했다가 다음 시작 합니다. 다음 호출 전에 레코드 집합을 닫아야 **BeginTrans** Jet의 요구 사항을 충족 하기 위해 합니다. 이 기술 노트에서는이 상황을 처리 하는 두 가지 방법을 설명 합니다.  
  
-   각 레코드 집합을 닫으면 **CommitTrans** 또는 **롤백** 작업 합니다.  
  
-   ODBC API 함수를 사용 하 여 **SQLFreeStmt**합니다.  
  
## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>각 CommitTrans 또는 롤백 작업 후 레코드 집합을 닫기  
 트랜잭션의 시작 하기 전에 recordset 개체 닫혀 있는지 확인 합니다. 호출한 후 **BeginTrans**, 레코드 집합의 호출 **열려** 멤버 함수입니다. 레코드 집합을 호출한 후 즉시 닫습니다 **CommitTrans** 또는 **롤백**합니다. Note 반복적으로 열고 닫아도 레코드 집합 응용 프로그램의 성능이 느려질 수 있습니다.  
  
## <a name="using-sqlfreestmt"></a>SQLFreeStmt를 사용 하 여  
 ODBC API 함수를 사용할 수도 있습니다 **SQLFreeStmt** 를 명시적으로 트랜잭션을 종료 커서를 닫습니다. 다른 트랜잭션이 시작 하려면 호출 **BeginTrans** 이어서 `CRecordset::Requery`합니다. 호출할 때 **SQLFreeStmt**, HSTMT 레코드 집합의 첫 번째 매개 변수로 지정 해야 하 고 **SQL_CLOSE** 두 번째 매개 변수로 합니다. 이 메서드는 결산 잔액과 개시 모든 트랜잭션의 시작 부분에 레코드 집합 보다 빠릅니다. 다음 코드에는이 기술을 구현 하는 방법을 보여 줍니다.  
  
```  
CMyDatabase db;  
db.Open("MYDATASOURCE");

CMyRecordset rs(&db);

 
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
// close the cursor  
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

 
// start transaction 2  
db.BeginTrans();

 
// now get the result set  
rs.Requery();

 
// manipulate data  
 
// end transaction 2  
db.CommitTrans();

 
rs.Close();

db.Close();
```  
  
 이 기술을 구현 하는 다른 방법은 새 함수를 작성 하는 것 **RequeryWithBeginTrans**, 커밋한 후 다음 트랜잭션이 시작 하기 위해 호출할 수 있으며 rollback 첫 번째입니다. 이러한 함수를 작성 하려면 다음 단계를 수행 합니다.  
  
1.  에 대 한 코드를 복사 **>crecordset:: Requery ()** 새 함수에 있습니다.  
  
2.  에 대 한 호출 직후에 다음 줄 추가 **SQLFreeStmt**:  
  
 `m_pDatabase->BeginTrans( );`  
  
 이제 트랜잭션의 각 쌍 사이이 함수를 호출할 수 있습니다.  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
// close the cursor,
    start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans();

 
// manipulate data  
 
// end transaction 2  
db.CommitTrans();
*// or Rollback()  
```  
  
> [!NOTE]
>  레코드 집합 멤버 변수를 변경 해야 할 경우이 방법을 사용 하지 마십시오 **m_strFilter** 또는 `m_strSort` 트랜잭션 간의 합니다. 각 레코드 집합을 종료 해야 경우 **CommitTrans** 또는 **롤백** 작업 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

