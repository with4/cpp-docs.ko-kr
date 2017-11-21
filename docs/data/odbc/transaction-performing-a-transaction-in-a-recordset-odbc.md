---
title: "트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1451775374b94bbefb6396e7afeda2396df84ba4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)
이 항목에서는 레코드 집합에서 트랜잭션을 수행 하는 방법에 설명 합니다.  
  
> [!NOTE]
>  트랜잭션 수준이 하나만 지원 됩니다. 트랜잭션을 중첩할 수 없습니다.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>레코드 집합에서 트랜잭션을 수행 하려면  
  
1.  호출 된 `CDatabase` 개체의 **BeginTrans** 멤버 함수입니다.  
  
2.  하지 대량 행 페치를 구현한 경우에 호출 된 **AddNew/업데이트**, **편집/업데이트**, 및 **삭제** 같은 하나 이상의 레코드 집합 개체의 멤버 함수 필요에 따라 여러 번 데이터베이스입니다. 자세한 내용은 참조 [레코드 집합: 추가, 업데이트 및 삭제 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)합니다. 대량 행 페치를 구현한 데이터 소스를 업데이트 하는 사용자 고유의 함수를 작성 해야 합니다.  
  
3.  마지막으로 호출 된 `CDatabase` 개체의 **CommitTrans** 멤버 함수입니다. 업데이트 중 하나에서 오류가 발생 하거나 변경 내용을 취소 하려면를 호출 하는 **롤백** 멤버 함수입니다.  
  
 다음 예제에서는 한 학생 학생이 등록 된 모든 클래스에서 제거 학교 등록 데이터베이스에서 삭제 하려면 두 개의 레코드 집합을 사용 합니다. 때문에 **삭제** 레코드 집합 모두에서 호출 성공 해야 하며, 트랜잭션이 필요 합니다. 이 예제에서는 있다고 가정 `m_dbStudentReg`, 형식의 멤버 변수 `CDatabase` 레코드 집합 클래스 및 데이터 원본에 이미 연결 `CEnrollmentSet` 및 `CStudentSet`합니다. `strStudentID` 변수에 사용자에 게 서 얻은 값을 포함 합니다.  
  
```  
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )  
{  
    // remove student from all the classes  
    // the student is enrolled in  
  
    if ( !m_dbStudentReg.BeginTrans( ) )  
        return FALSE;  
  
    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);  
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    CStudentSet rsStudentSet(&m_dbStudentReg);  
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsStudentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    TRY  
    {  
        while ( !rsEnrollmentSet.IsEOF( ) )  
        {  
            rsEnrollmentSet.Delete( );  
            rsEnrollmentSet.MoveNext( );  
        }  
  
        // delete the student record  
        rsStudentSet.Delete( );  
  
        m_dbStudentReg.CommitTrans( );  
    }  
  
    CATCH_ALL(e)  
    {  
        m_dbStudentReg.Rollback( );  
        return FALSE;  
    }  
    END_CATCH_ALL  
  
    rsEnrollmentSet.Close( );  
    rsStudentSet.Close( );  
  
    return TRUE;  
  
}  
```  
  
> [!NOTE]
>  호출 **BeginTrans** 호출 하지 않고 다시 **CommitTrans** 또는 **롤백** 오류가 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)   
 [트랜잭션: 트랜잭션이 미치는 영향 (ODBC) 업데이트](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)