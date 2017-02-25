---
title: "트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC) | Microsoft Docs"
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
  - "트랜잭션, 레코드 집합 업데이트"
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 레코드 집합에서 트랜잭션을 수행하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  한 수준의 트랜잭션만 지원되며 트랜잭션을 중첩할 수 없습니다.  
  
#### 레코드 집합에서 트랜잭션을 수행하려면  
  
1.  `CDatabase` 개체의 **BeginTrans** 멤버 함수를 호출합니다.  
  
2.  대량 행 페치를 구현하지 않은 경우 데이터베이스에 있는 한 개 이상의 레코드 집합 개체에서 **AddNew\/Update**, **Edit\/Update** 및 **Delete** 멤버 함수를 필요한 만큼 호출합니다.  자세한 내용은 [레코드 집합: 레코드 추가, 업데이트 및 삭제\(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)를 참조하십시오.  대량 행 페치를 구현한 경우 직접 데이터 소스를 업데이트하는 함수를 작성합니다.  
  
3.  마지막으로 `CDatabase` 개체의 **CommitTrans** 멤버 함수를 호출합니다.  업데이트 중 하나에서 오류가 발생하거나 변경 내용을 취소하려면 **Rollback** 멤버 함수를 호출합니다.  
  
 다음 예제는 레코드 집합 두 개를 사용하여 한 학생을 학교의 등록 데이터베이스에서 삭제하고 등록되어 있는 모든 클래스에서 제거합니다.  두 레코드 집합 모두에서 성공적으로 **Delete**를 호출해야 하므로 트랜잭션이 필요합니다.  이 예제에서는 레코드 집합 클래스인 `CEnrollmentSet` 및 `CStudentSet`, 그리고 이미 데이터 소스에 연결되어 있는 `CDatabase` 형식의 멤버 변수인 `m_dbStudentReg`가 있다고 가정합니다.  `strStudentID` 변수는 사용자가 입력한 값을 가지고 있습니다.  
  
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
>  **CommitTrans**나 **Rollback**을 호출하지 않고 **BeginTrans**를 다시 호출하면 오류가 발생합니다.  
  
## 참고 항목  
 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [트랜잭션: 트랜잭션이 업데이트에 미치는 영향\(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)