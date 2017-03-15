---
title: "레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC) | Microsoft Docs"
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
  - "AddNew 메서드"
  - "레코드 집합의 데이터[C++]"
  - "ODBC 레코드 집합[C++], 레코드 추가"
  - "ODBC 레코드 집합[C++], 레코드 삭제"
  - "ODBC 레코드 집합[C++], 레코드 편집"
  - "레코드 편집[C++], 레코드 집합"
  - "레코드[C++], 추가"
  - "레코드[C++], 레코드 집합에서 삭제"
  - "레코드[C++], 편집"
  - "레코드[C++], 업데이트"
  - "레코드 집합[C++], 레코드 추가"
  - "레코드 집합[C++], 레코드 삭제"
  - "레코드 집합[C++], 레코드 편집"
  - "레코드 집합[C++], 업데이트"
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 `CRecordset` 클래스의 `AddNew`, **Edit** 및 **Delete** 멤버 함수가 작동하는 방식에 대해 설명합니다.  다음 내용에 대해 다룹니다.  
  
-   [레코드 추가 방법](#_core_adding_a_record)  
  
-   [추가된 레코드 표시](#_core_visibility_of_added_records)  
  
-   [레코드 편집 방법](#_core_editing_an_existing_record)  
  
-   [레코드 삭제 방법](#_core_deleting_a_record)  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 사용하는 경우 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 위의 내용을 보충하는 자료로 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)이 있습니다. 이 항목에서는 업데이트 작업에서 RFX의 역할을 설명합니다.  
  
##  <a name="_core_adding_a_record"></a> 레코드 추가  
 레코드 집합에 새 레코드를 추가하려면 레코드 집합의 [AddNew](../Topic/CRecordset::AddNew.md) 멤버 함수를 호출하고 새 레코드의 필드 데이터 멤버 값을 설정하고, [Update](../Topic/CRecordset::Update.md) 멤버 함수를 호출하여 데이터 소스에 레코드를 작성해야 합니다.  
  
 `AddNew`를 호출하려면 레코드 집합을 읽기 전용으로 열지 않아야 합니다.  `CanUpdate` 및 `CanAppend` 멤버 함수를 사용하여 이러한 조건을 확인할 수 있습니다.  
  
 `AddNew`를 호출하면 다음과 같은 작업이 수행됩니다.  
  
-   편집 버퍼에 있는 레코드가 저장됩니다. 따라서 작업을 취소해도 레코드의 내용을 복원할 수 있습니다.  
  
-   필드 데이터 멤버에 플래그가 지정되므로 나중에 변경 내용을 찾을 수 있습니다.  또한 필드 데이터 멤버가 클린\(변경되지 않음\)으로 표시되고 Null로 설정됩니다.  
  
 사용자가 `AddNew`를 호출하고 나면 편집 버퍼는 값을 채울 수 있는 새로운 빈 레코드를 나타냅니다.  레코드에 값을 채우려면 수동으로 값을 할당하여 설정합니다.  필드에 실제 데이터 값을 지정하지 않고 `SetFieldNull`을 호출하여 Null 값을 지정합니다.  
  
 변경 내용을 커밋하려면 **Update**를 호출합니다.  새 레코드에 대해 **Update**를 호출하면 다음과 같은 작업이 수행됩니다.  
  
-   ODBC 드라이버에서 **::SQLSetPos** ODBC API 함수를 지원하는 경우 MFC에서는 이 함수를 사용하여 데이터 소스에 레코드를 추가합니다.  **::SQLSetPos**를 사용하면 MFC에서 SQL 문을 생성하거나 처리할 필요가 없기 때문에 레코드를 더 효과적으로 추가할 수 있습니다.  
  
-   **::SQLSetPos**를 사용할 수 없는 경우 MFC에서는 다음을 수행합니다.  
  
    1.  변경 내용이 발견되지 않으면 **Update**는 아무 작업도 수행하지 않고 0을 반환합니다.  
  
    2.  변경 내용이 있으면 **Update**는 SQL **INSERT** 문을 생성합니다.  모두 더티 필드 데이터 멤버로 표시되는 열이 **INSERT** 문에서 나열됩니다.  열을 포함시키려면 [SetFieldDirty](../Topic/CRecordset::SetFieldDirty.md) 멤버 함수를 호출합니다.  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  **Update**가 새 레코드를 커밋합니다. 이때 트랜잭션이 진행 중이 아니면 **INSERT** 문이 실행되어 레코드가 데이터 소스의 테이블 및 레코드 집합\(스냅숏이 아닌 경우\)에 커밋됩니다.  
  
    4.  저장된 레코드가 편집 버퍼에 복원됩니다.  **INSERT** 문이 성공적으로 실행되었는지 여부에 관계없이 `AddNew` 호출 이전의 현재 레코드가 다시 현재 레코드로 표시됩니다.  
  
    > [!TIP]
    >  새 레코드를 완벽하게 제어하려면 다음의 방법을 따르십시오. \(a\)값을 가질 모든 필드에 값을 설정합니다. \(b\)Null로 남을 모든 필드에 대해 필드의 포인터와 매개 변수 **TRUE**\(기본값\)를 사용하여 `SetFieldNull`을 호출하여 명시적으로 필드를 설정합니다.  필드가 데이터 소스에 쓰여지지 않게 하려면 필드의 포인터와 매개 변수 **FALSE**를 사용하여 `SetFieldDirty`를 호출하고 필드의 값은 수정하지 않습니다.  필드에 Null을 사용할 수 있는지 여부를 확인하려면 `IsFieldNullable`을 호출합니다.  
  
    > [!TIP]
    >  레코드 집합 데이터 멤버의 값이 변경될 때 이를 감지하기 위해 MFC에서는 레코드 집합에 저장할 수 있는 각 데이터 형식에 적합한 **PSEUDO\_NULL** 값을 사용합니다.  필드를 명시적으로 **PSEUDO\_NULL** 값으로 설정해야 하는 경우 필드가 이미 Null로 표시되어 있더라도 `SetFieldNull`을 호출하여 첫째 매개 변수에는 필드 주소를, 둘째 매개 변수에는 **FALSE**를 전달해야 합니다.  
  
##  <a name="_core_visibility_of_added_records"></a> 추가된 레코드 표시  
 추가된 레코드를 레코드 집합에서 언제 볼 수 있습니까?  추가된 레코드를 볼 수 있고 없고는 다음 두 가지에 따라 달라집니다.  
  
-   드라이버의 기능  
  
-   프레임워크에서 활용할 수 있는 함수  
  
 ODBC 드라이버에서 **::SQLSetPos** ODBC API 함수를 지원하는 경우 MFC에서는 이 함수를 사용하여 레코드를 추가합니다.  **::SQLSetPos**를 사용하면 업데이트 가능한 모든 MFC 레코드 집합에서 추가된 레코드를 볼 수 있습니다.  이 함수가 지원되지 않는 경우 추가된 레코드를 볼 수 없고, 보려면 **Requery**를 호출해야 합니다.  이 경우 **::SQLSetPos**를 사용하는 것이 더 효과적입니다.  
  
##  <a name="_core_editing_an_existing_record"></a> 기존 레코드 편집  
 레코드 집합의 기존 레코드를 편집하려면 해당 레코드로 스크롤하고 레코드 집합의 [Edit](../Topic/CRecordset::Edit.md) 멤버 함수를 호출한 다음, 새 레코드의 필드 데이터 멤버를 설정하고 [Update](../Topic/CRecordset::Update.md) 멤버 함수를 호출하여 변경된 레코드를 데이터 소스에 써야 합니다.  
  
 **Edit**를 호출하려면 먼저 레코드 집합이 업데이트 가능하고 해당 레코드에 있어야 합니다.  `CanUpdate` 및 `IsDeleted` 멤버 함수를 사용하여 이러한 조건을 확인할 수 있습니다.  또한 현재 레코드가 아직 삭제되지 않았어야 하며 레코드 집합에 레코드가 있어야 합니다. 즉 `IsBOF`와 `IsEOF` 모두 0을 반환해야 합니다.  
  
 **Edit**를 호출하면 편집 버퍼의 레코드, 즉 현재 레코드가 저장됩니다.  저장된 레코드의 값은 나중에 필드가 변경되었는지 여부를 검색하는 데 사용됩니다.  
  
 **Edit**를 호출한 후 편집 버퍼에는 여전히 현재 레코드가 표시되지만 필드 데이터 멤버의 변경 내용을 적용할 수 있도록 준비된 상태입니다.  레코드를 변경하려면 편집할 모든 필드 데이터 멤버의 값을 사용자가 직접 설정합니다.  필드에 실제 데이터 값을 지정하지 않고 `SetFieldNull`을 호출하여 Null 값을 지정합니다.  변경 내용을 커밋하려면 **Update**를 호출합니다.  
  
> [!TIP]
>  `AddNew` 또는 **Edit** 모드를 끝내려면 **AFX\_MOVE\_REFRESH** 매개 변수를 사용하여 **Move**를 호출합니다.  
  
 **Update**를 호출하려면 먼저 레코드 집합이 비어 있고 현재 레코드가 삭제되어 있지 않아야 합니다.  즉 `IsBOF`, `IsEOF` 및 `IsDeleted`가 모두 0을 반환해야 합니다.  
  
 편집한 레코드에 대해 **Update**를 호출하면 다음과 같은 작업이 수행됩니다.  
  
-   ODBC 드라이버에서 **::SQLSetPos** ODBC API 함수를 지원하는 경우 MFC에서는 이 함수를 사용하여 데이터 소스에서 레코드를 업데이트합니다.  드라이버는 **::SQLSetPos**를 사용하여 편집 버퍼를 서버에 있는 해당 레코드와 비교하고 서로 다르면 서버에 있는 레코드를 업데이트합니다.  **::SQLSetPos**를 사용하면 MFC에서 SQL 문을 생성하거나 처리할 필요가 없기 때문에 레코드를 더 효과적으로 업데이트할 수 있습니다.  
  
     또는  
  
-   **::SQLSetPos**를 사용할 수 없는 경우 MFC에서는 다음을 수행합니다.  
  
    1.  변경 내용이 없으면 **Update**는 아무 작업도 수행하지 않고 0을 반환합니다.  
  
    2.  변경 내용이 있으면 **Update**는 SQL **UPDATE** 문을 생성합니다.  **UPDATE** 문에 나열되는 열은 변경된 필드 데이터 멤버에 기반합니다.  
  
    3.  **Update**가 변경 내용을 커밋\(**UPDATE** 문을 실행\)하고 데이터 소스에서 레코드가 변경됩니다. 트랜잭션이 진행 중이면 커밋되지 않습니다. 트랜잭션이 업데이트에 주는 영향에 대한 자세한 내용은 [트랜잭션: 레코드 집합에서 트랜잭션 수행\(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)을 참조하십시오.  ODBC는 또한 변경되는 레코드의 복사본을 보존합니다.  
  
    4.  `AddNew` 프로세스와 달리 **Edit** 프로세스는 저장된 레코드를 복원하지 않습니다.  편집한 레코드는 현재 레코드로 남습니다.  
  
    > [!CAUTION]
    >  **Update**를 호출하여 레코드 집합을 업데이트하기 전에 레코드 집합은 테이블의 기본 키를 구성하는 모든 열 또는 테이블에 있는 고유 인덱스의 모든 열이나 행을 식별할 수 있는 열을 포함해야 합니다.  때로 프레임워크에서는 레코드 집합에서 선택된 열만을 사용하여 테이블에서 업데이트할 레코드를 식별할 수도 있습니다.  필요한 열을 모두 포함하지 않으면 테이블에서 여러 레코드가 업데이트될 수도 있습니다.  이 경우 **Update**를 호출하면 프레임워크가 예외를 throw합니다.  
  
    > [!TIP]
    >  `AddNew` 또는 **Edit** 함수를 호출한 다음 **Update**를 호출하기 전에 두 함수 중 하나를 다시 호출하면 편집 버퍼는 저장된 레코드로 새로 고쳐지고 작업 중인 새 레코드 또는 편집된 레코드가 대체됩니다.  이 방법을 사용하면 `AddNew` 또는 **Edit**를 중단하고 새로 시작할 수 있습니다. 작업 중인 레코드에 오류가 있다고 판단되면 **Edit** 또는 `AddNew`를 다시 호출하면 됩니다.  
  
##  <a name="_core_deleting_a_record"></a> 레코드 삭제  
 레코드 집합에서 레코드를 삭제하려면 해당 레코드로 스크롤하고 레코드 집합의 [Delete](../Topic/CRecordset::Delete.md) 멤버 함수를 호출합니다.  `AddNew`나 **Edit**와 달리 **Delete**를 사용할 때는 **Update**를 호출할 필요가 없습니다.  
  
 **Delete**를 호출하려면 먼저 레코드 집합이 업데이트 가능하고 해당 레코드에 있어야 합니다.  `CanUpdate`, `IsBOF`, `IsEOF` 및 `IsDeleted` 멤버 함수를 사용하여 이러한 조건을 확인할 수 있습니다.  
  
 **Delete**를 호출하면 다음과 같은 작업이 수행됩니다.  
  
-   ODBC 드라이버에서 **::SQLSetPos** ODBC API 함수를 지원하는 경우 MFC에서는 이 함수를 사용하여 데이터 소스에서 레코드를 삭제합니다.  대개 SQL보다 **::SQLSetPos**를 사용하는 것이 더 효과적입니다.  
  
     또는  
  
-   **::SQLSetPos**를 사용할 수 없는 경우 MFC에서는 다음을 수행합니다.  
  
    1.  `AddNew`나 **Edit**와 달리 편집 버퍼에 있는 현재 레코드를 백업하지 않습니다.  
  
    2.  **Delete**는 레코드를 제거할 SQL **DELETE** 문을 생성합니다.  
  
         `AddNew`나 **Edit**와 달리 편집 버퍼에 있는 현재 레코드가 저장되지 않습니다.  
  
    3.  **Delete**가 삭제 작업을 커밋\(**DELETE** 문 실행\)합니다.  레코드가 데이터 소스 및 ODBC\(레코드가 스냅숏인 경우\)에서 삭제된 것으로 표시됩니다.  
  
    4.  삭제된 레코드의 값은 여전히 레코드 집합의 필드 데이터 멤버에 남지만 필드 데이터 멤버는 Null로 표시되고 레코드 집합의 `IsDeleted` 멤버 함수는 0 이외의 값을 반환합니다.  
  
    > [!NOTE]
    >  레코드를 삭제하고 나면 다른 레코드로 스크롤하여 편집 버퍼를 새 레코드의 데이터로 다시 채워야 합니다.  **Delete**를 다시 호출하거나 **Edit**를 호출하면 오류가 발생합니다.  
  
 업데이트 작업에 사용되는 SQL 문에 대한 자세한 내용은 [SQL](../../data/odbc/sql.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 업데이트에 대한 추가 정보\(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md)   
 [RFX](../../data/odbc/record-field-exchange-rfx.md)