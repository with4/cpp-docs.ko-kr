---
title: "레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC) | Microsoft Docs"
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
  - "AddNew 메서드"
  - "레코드 집합의 데이터[C++]"
  - "ODBC 레코드 집합[C++], 레코드 추가"
  - "ODBC 레코드 집합[C++], 레코드 삭제"
  - "ODBC 레코드 집합[C++], 레코드 편집"
  - "레코드 편집[C++]"
  - "레코드 편집[C++], 레코드 집합"
  - "레코드[C++], 추가"
  - "레코드[C++], 제거"
  - "레코드[C++], 편집"
  - "레코드[C++], 업데이트"
  - "레코드 집합[C++], 레코드 추가"
  - "레코드 집합[C++], 레코드 삭제"
  - "레코드 집합[C++], 레코드 편집"
  - "레코드 집합[C++], 업데이트"
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
> [!NOTE]
>  이제 더 효율적으로 대량 레코드를 추가할 수 있습니다.  자세한 내용은 [레코드 집합: 대량 레코드 추가\(ODBC\)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md)를 참조하십시오.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 사용하는 경우 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 업데이트 가능한 스냅숏과 다이너셋을 사용하면 레코드를 추가, 편집\(업데이트\) 및 삭제할 수 있습니다.  다음은 이 항목에서 설명하는 내용입니다.  
  
-   [레코드 집합이 업데이트 할 수 있는지 확인](#_core_determining_whether_your_recordset_is_updatable).  
  
-   [레코드 집합에 레코드 추가](#_core_adding_a_record_to_a_recordset).  
  
-   [레코드 집합에서 레코드 편집](#_core_editing_a_record_in_a_recordset).  
  
-   [레코드 집합에서 레코드 삭제](#_core_deleting_a_record_from_a_recordset).  
  
 업데이트가 이루어지는 방법 및 업데이트가 다른 사용자에게 표시되는 방법에 대한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 참조하십시오.  일반적으로 레코드를 추가, 편집 또는 삭제하면 레코드 집합에서 데이터 소스를 즉시 변경하지만  관련 업데이트 그룹을 트랜잭션으로 일괄 처리할 수도 있습니다.  트랜잭션이 진행 중이면 트랜잭션을 커밋할 때까지 업데이트는 최종 상태가 되지 않으므로  필요한 경우 변경 내용을 롤백할 수 있습니다.  트랜잭션에 대한 자세한 내용은 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)을 참조하십시오.  
  
 다음 표에서는 서로 다른 업데이트 특성을 갖는 레코드 집합에 사용할 수 있는 옵션이 요약되어 있습니다.  
  
### 레코드 집합 읽기\/업데이트 옵션  
  
|형식|Read|레코드 편집|레코드 삭제|새로 추가\(추가\)|  
|--------|----------|------------|------------|-----------------|  
|읽기 전용|Y|N|N|N|  
|추가 전용|Y|N|N|Y|  
|완전 업데이트 가능|Y|Y|Y|Y|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> 레코드 집합의 업데이트 가능 여부 확인  
 데이터 소스를 업데이트할 수 있고 업데이트 가능한 레코드 집합을 연 경우 해당 레코드 집합 개체를 업데이트할 수 있습니다.  레코드 집합 개체가 업데이트 가능한지 여부는 사용하는 SQL 문, ODBC 드라이버의 기능, ODBC 커서 라이브러리가 메모리에 있는지 여부 등에 의해서도 달라집니다.  읽기 전용 레코드 집합이나 데이터 소스는 업데이트할 수 없습니다.  
  
#### 레코드 집합의 업데이트 가능 여부를 확인하려면  
  
1.  레코드 집합 개체의 [CanUpdate](../Topic/CRecordset::CanUpdate.md) 멤버 함수를 호출합니다.  
  
     `CanUpdate`는 레코드 집합을 업데이트할 수 있으면 0 이외의 값을 반환합니다.  
  
 기본적으로 레코드 집합은 완전히 업데이트할 수 있으며 이는 `AddNew`, **Edit**, **Delete** 작업을 수행할 수 있습니다.  그러나 [appendOnly](../Topic/CRecordset::Open.md) 옵션을 사용하여 업데이트 가능한 레코드 집합을 열 수도 있습니다.  이 방법으로 레코드 집합을 연 경우 `AddNew`를 사용하여 새 레코드를 추가할 수만 있고  기존 레코드를 편집하거나 삭제할 수 없습니다.  [CanAppend](../Topic/CRecordset::CanAppend.md) 멤버 함수를 호출하여 레코드 집합이 추가를 위해서만 열려 있는지 테스트할 수 있습니다.  레코드 집합이 완전히 업데이트 가능하거나 추가를 위해서만 열려 있는 경우 `CanAppend`는 0이 아닌 값을 반환합니다.  
  
 다음 코드에서는 `rsStudentSet`라는 레코드 집합 개체에 대해 `CanUpdate`를 사용하는 방법을 보여 줍니다.  
  
```  
if( !rsStudentSet.Open( ) )  
    return FALSE;  
if( !rsStudentSet.CanUpdate( ) )  
{  
    AfxMessageBox( "Unable to update the Student recordset." );  
    return;  
}  
```  
  
> [!CAUTION]
>  **Update**를 호출하여 레코드 집합을 업데이트하기 전에 레코드 집합에는 테이블의 기본 키를 구성하는 모든 열 또는 테이블에 있는 고유 인덱스의 모든 열을 포함되어 있어야 합니다.  때로 프레임워크에서는 레코드 집합에서 선택된 열만을 사용하여 테이블에서 업데이트할 레코드를 식별할 수도 있습니다.  필요한 열이 모두 포함되어 있지 않으면 테이블에서 여러 레코드가 업데이트되어 테이블의 참조 무결성이 손상될 수 있습니다.  이 경우 **Update**를 호출하면 프레임워크가 예외를 throw합니다.  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a> 레코드 집합에 레코드 추가  
 레코드 집합의 [CanAppend](../Topic/CRecordset::CanAppend.md) 멤버 함수에서 0 이외의 값을 반환하면 레코드 집합에 새 레코드를 추가할 수 있습니다.  
  
#### 레코드 집합에 새 레코드를 추가하려면  
  
1.  레코드 집합의 속성에서 추가 가능한지 확인합니다.  
  
2.  레코드 집합 개체의 [AddNew](../Topic/CRecordset::AddNew.md) 멤버 함수를 호출합니다.  
  
     `AddNew`는 해당 레코드 집합이 편집 버퍼의 역할을 하도록 준비합니다.  모든 필드 데이터 멤버를 특수 값 Null로 설정하고 변경되지 않은 것으로 표시하여 [Update](../Topic/CRecordset::Update.md)를 호출할 때 변경된\(더티\) 값만 데이터 소스에 기록되도록 합니다.  
  
3.  새 레코드의 필드 데이터 멤버 값을 설정합니다.  
  
     필드 데이터 멤버에 값을 할당합니다.  값을 할당하지 않은 필드 데이터 멤버는 데이터 소스에 기록되지 않습니다.  
  
4.  레코드 집합 개체의 **Update** 멤버 함수를 호출합니다.  
  
     **Update** 멤버 함수는 데이터 소스에 새 레코드를 기록하여 추가 작업을 끝냅니다.  **Update**에 실패하면 발생하는 상황에 대한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 참조하십시오.  
  
 레코드 추가 작업의 작동 방식 및 추가된 레코드가 레코드 집합에 표시되는 시기에 대한 자세한 내용은 [레코드 집합: AddNew, Edit 및 Delete의 작동 방식\(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)을 참조하십시오.  
  
 다음 예제는 새 레코드를 추가하는 방법을 보여 줍니다.  
  
```  
if( !rsStudent.Open( ) )  
    return FALSE;  
if( !rsStudent.CanAppend( ) )  
    return FALSE;                      // no field values were set  
rsStudent.AddNew( );  
rsStudent.m_strName = strName;  
rsStudent.m_strCity = strCity;  
rsStudent.m_strStreet = strStreet;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not added; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  `AddNew` 또는 **Edit** 호출을 취소하려면 `AddNew` 또는 **Edit**를 다시 호출하거나 **AFX\_MOVE\_REFRESH** 매개 변수를 사용하여 **Move**를 호출합니다.  그러면 데이터 멤버는 이전 값으로 다시 설정되어 **Edit** 또는 **Add** 모드로 남아 있게 됩니다.  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a> 레코드 집합에서 레코드 편집  
 레코드 집합의 [CanUpdate](../Topic/CRecordset::CanUpdate.md) 멤버 함수가 0 이외의 값을 반환하는 경우 기존 레코드를 편집할 수 있습니다.  
  
#### 레코드 집합에서 기존 레코드를 편집하려면  
  
1.  레코드 집합을 업데이트할 수 있는지 확인합니다.  
  
2.  업데이트할 레코드로 스크롤합니다.  
  
3.  레코드 집합 개체의 [Edit](../Topic/CRecordset::Edit.md) 멤버 함수를 호출합니다.  
  
     **Edit** 멤버 함수는 해당 레코드 집합이 편집 버퍼의 역할을 하도록 준비합니다.  모든 필드 데이터 멤버는 표시가 되므로 나중에 레코드 집합에서 필드 데이터 멤버가 변경되었는지 여부를 알 수 있습니다.  [Update](../Topic/CRecordset::Update.md)를 호출하면 변경된 필드 데이터 멤버의 새 값이 데이터 소스에 기록됩니다.  
  
4.  새 레코드의 필드 데이터 멤버 값을 설정합니다.  
  
     필드 데이터 멤버에 값을 할당합니다.  값이 할당되지 않은 필드 데이터 멤버는 변경되지 않은 상태로 유지됩니다.  
  
5.  레코드 집합 개체의 **Update** 멤버 함수를 호출합니다.  
  
     **Update** 멤버 함수는 변경된 레코드를 데이터 소스에 기록하여 편집을 끝냅니다.  **Update**에 실패하면 발생하는 상황에 대한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 참조하십시오.  
  
 레코드를 편집한 후 편집된 레코드는 현재 레코드로 남습니다.  
  
 다음 예제에서는 **Edit** 작업을 보여 줍니다.  이 예제에서는 사용자가 편집하려는 레코드로 이동했다고 가정합니다.  
  
```  
rsStudent.Edit( );  
rsStudent.m_strStreet = strNewStreet;  
rsStudent.m_strCity = strNewCity;  
rsStudent.m_strState = strNewState;  
rsStudent.m_strPostalCode = strNewPostalCode;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not updated; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  `AddNew` 또는 **Edit** 호출을 취소하려면 `AddNew` 또는 **Edit**를 다시 호출하거나 **AFX\_MOVE\_REFRESH** 매개 변수를 사용하여 **Move**를 호출합니다.  그러면 데이터 멤버는 이전 값으로 다시 설정되어 **Edit** 또는 **Add** 모드로 남아 있게 됩니다.  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a> 레코드 집합에서 레코드 삭제  
 레코드 집합의 [CanUpdate](../Topic/CRecordset::CanUpdate.md) 멤버 함수가 0 이외의 값을 반환하는 경우 레코드를 삭제할 수 있습니다.  
  
#### 레코드를 삭제하려면  
  
1.  레코드 집합을 업데이트할 수 있는지 확인합니다.  
  
2.  업데이트할 레코드로 스크롤합니다.  
  
3.  레코드 집합 개체의 [Delete](../Topic/CRecordset::Delete.md) 멤버 함수를 호출합니다.  
  
     **Delete**는 즉시 레코드 집합과 데이터 소스 모두에서 레코드를 삭제된 것으로 표시합니다.  
  
     `AddNew` 및 **Edit**와 달리 **Delete**에는 해당 **Update**가 호출되지 않습니다.  
  
4.  다른 레코드로 스크롤합니다.  
  
    > [!NOTE]
    >  레코드 집합에서 이동할 때 삭제된 레코드를 건너뛰지 않을 수도 있습니다.  자세한 내용은 [IsDeleted](../Topic/CRecordset::IsDeleted.md) 멤버 함수를 참조하십시오.  
  
 다음 예제에서는 **Delete** 작업을 보여 줍니다.  이 예제에서는 사용자가 삭제하려는 레코드로 이동했다고 가정합니다.  **Delete**를 호출한 후 새 레코드로 이동해야 합니다.  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 `AddNew`, **Edit**, **Delete** 멤버 함수의 효과에 대한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 잠금\(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)