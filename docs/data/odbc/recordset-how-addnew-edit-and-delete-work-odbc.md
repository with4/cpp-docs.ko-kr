---
title: '레코드 집합: AddNew, Edit 및 Delete 작동 방식 (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e3d9dc82f4ea31557c4ec330b9737579021a8d35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094132"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에서는 설명 방법을 `AddNew`, **편집**, 및 **삭제** 클래스의 멤버 함수 `CRecordset` 작동 합니다. 다루는 항목은 다음과 같습니다.  
  
-   [레코드 추가 방법](#_core_adding_a_record)  
  
-   [추가 된 레코드 표시](#_core_visibility_of_added_records)  
  
-   [레코드 편집 방법](#_core_editing_an_existing_record)  
  
-   [레코드 삭제 방법](#_core_deleting_a_record)  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 읽을 하려는 보완, [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md), RFX의 업데이트 작업에 해당 역할을 설명 하는 합니다.  
  
##  <a name="_core_adding_a_record"></a> 레코드 추가  

 레코드 집합의 호출에서는 레코드 집합에 새 레코드를 추가 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 새 레코드의 필드 데이터 멤버의 값을 설정 하 고 호출 된 멤버 함수는 [업데이트](../../mfc/reference/crecordset-class.md#update) 작성 하는 멤버 함수 데이터 원본에는 레코드입니다.  
  
 호출에 대 한 전제 조건으로 `AddNew`, 레코드 집합 해야 열지 읽기 전용으로 합니다. `CanUpdate` 및 `CanAppend` 멤버 함수를 사용 하 여 이러한 조건을 확인할 수 있습니다.  
  
 호출 하는 경우 `AddNew`:  
  
-   작업이 취소 되는 경우 해당 콘텐츠를 복원할 수 레코드 편집 버퍼에 저장 됩니다.  
  
-   필드 데이터 멤버에는 나중에 변경 내용을 찾을 수 있도록 플래그가 지정 됩니다. 필드 데이터 멤버에도 표시 됩니다 (변경 되지 않음) 정리 하 고 Null로 설정 합니다.  
  
 호출한 후 `AddNew`, 편집 버퍼를 나타내는 새, 빈 레코드를 값을 채울 수 있습니다. 이 위해 직접 설정한 값을 할당 하 여 합니다. 실제 데이터 값 필드를 지정 하지 않고 호출할 수 있습니다 `SetFieldNull` Null 값을 지정 합니다.  
  
 변경 내용을 커밋한을 호출 하면 **업데이트**합니다. 호출 하는 경우 **업데이트** 새 레코드에 대해:  
  
-   ODBC 드라이버가 지원는 **:: SQLSetPos** MFC ODBC API 함수는 함수를 사용 하 여 데이터 원본에서 레코드를 추가 합니다. 와 **:: SQLSetPos**, MFC 레코드를 추가할 수 보다 효율적으로 생성 하 고 SQL 문을 처리 하는 없기 때문입니다.  
  
-   경우 **:: SQLSetPos** 수 없습니다을 사용 하는 MFC에서 다음을 수행 합니다.  
  
    1.  변경 내용을 감지 되 면 **업데이트** 없으며 0을 반환 합니다.  
  
    2.  변경 된 경우 **업데이트** SQL 생성 **삽입** 문. 모든 더티 필드 데이터 멤버에 표시 되는 열에 나열 되는 **삽입** 문. 포함 되도록 열을 강제로 표시 하려면 호출는 [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) 멤버 함수:  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  **업데이트** 새 레코드를 커밋합니다-는 **삽입** 문을 실행 하 고 레코드 표시 되지 않으면 데이터 원본 (및 레코드 집합 되지 않은 경우 스냅숏)의 테이블에 커밋된 트랜잭션이 진행 중입니다.  
  
    4.  저장된 된 레코드 편집 버퍼도 복원 됩니다. 이전의 현재 레코드는 `AddNew` 호출 되 든 관계 없이 다시 현재는 **삽입** 문이 성공적으로 실행 합니다.  
  
    > [!TIP]
    >  새 레코드의 완전 하 게 제어에 대 한 다음과 같은 접근: 값이 되며 다음 호출 하 여 Null 유지 되는 모든 필드를 명시적으로 설정 하는 필드의 값을 설정 `SetFieldNull` 완벽 하 게 필드 및 매개 변수 **TRUE**  (기본값). 필드 데이터 원본, 호출에 기록 되지 않습니다 보장 하려는 경우 `SetFieldDirty` 완벽 하 게 필드 및 매개 변수 **FALSE**, 고 필드의 값을 수정 하지 않습니다. 필드는 Null이 될 수 있는지 여부를 확인 하려면 호출 `IsFieldNullable`합니다.  
  
    > [!TIP]
    >  MFC 사용 하 여 레코드 집합 데이터 멤버 값을 변경 하는 경우를 검색 하려면는 **PSEUDO_NULL** 레코드 집합에 저장할 수 있는 각 데이터 형식에 적절 한 값입니다. 명시적 필드를 설정 해야 하는 경우는 **PSEUDO_NULL** 값과 필드 Null을 표시 하려면 이미 발생도 호출 해야 `SetFieldNull`, 첫 번째 매개 변수에서 필드의 주소를 전달 하 고 **FALSE**에서 두 번째 매개 변수입니다.  
  
##  <a name="_core_visibility_of_added_records"></a> 추가 된 레코드 표시  
 추가 된 레코드를 레코드 집합 표시 인가요? 추가 된 레코드가 있고 경우에 따라 두 가지 작업에 따라 표시 되지 않습니다.  
  
-   드라이버는 수 있습니다.  
  
-   어떤 프레임 워크 활용할 수 있습니다.  
  
 ODBC 드라이버가 지원는 **:: SQLSetPos** MFC ODBC API 함수는 함수를 사용 하 여 레코드를 추가 합니다. 와 **:: SQLSetPos**, 추가 된 레코드를 업데이트할 수 있는 모든 MFC 레코드 집합으로 볼 수 있습니다. 함수에 대 한 지원, 추가 된 레코드가 표시 되는 호출 해야 **Requery** 를 보겠습니다. 사용 하 여 **:: SQLSetPos** 효율적입니다.  
  
##  <a name="_core_editing_an_existing_record"></a> 기존 레코드를 편집  
 레코드 집합에서 기존 레코드를 편집 하려면 레코드 집합의 레코드를 하려면 스크롤하고 [편집](../../mfc/reference/crecordset-class.md#edit) 새 레코드의 필드 데이터 멤버의 값을 설정 하 고 호출 된 멤버 함수는 [업데이트](../../mfc/reference/crecordset-class.md#update)멤버 함수를 데이터 소스에 변경 된 레코드를 기록 합니다.  
  
 호출에 대 한 전제 조건으로 **편집**, 업데이트 가능 하 고 레코드에서 해당 레코드 있어야 합니다. `CanUpdate` 및 `IsDeleted` 멤버 함수를 사용 하 여 이러한 조건을 확인할 수 있습니다. 또한 현재 레코드가 이미 삭제 되지 않으며 레코드 집합에 레코드가 있어야 합니다. (둘 다 `IsBOF` 및 `IsEOF` 0을 반환).  
  
 호출 하는 경우 **편집**, 레코드 편집 버퍼 (현재 레코드)에 저장 됩니다. 저장 된 레코드의 값 필드가 변경 되었는지 여부를 검색 하려면 나중에 사용 됩니다.  
  
 호출한 후 **편집**, 편집 버퍼는 여전히 현재 레코드 표시 되지만 필드 데이터 멤버의 변경 내용을 받아들일 준비가 되었습니다. 레코드를 변경 하려면 수동으로 편집 하려는 필드 데이터 멤버의 값을 설정할 수 있습니다. 실제 데이터 값 필드를 지정 하지 않고 호출할 수 있습니다 `SetFieldNull` Null 값을 지정 합니다. 변경 내용을 커밋한 호출 **업데이트**합니다.  
  
> [!TIP]
>  활용 `AddNew` 또는 **편집** 모드, 호출 **이동** 매개 변수와 함께 **AFX_MOVE_REFRESH**합니다.  
  
 호출에 대 한 전제 조건으로 **업데이트**, 레코드 집합을 입력 해야 합니다. 및 현재 레코드가 삭제 되지 않아야 합니다. `IsBOF``IsEOF`, 및 `IsDeleted` 0을 모두 반환 되어야 합니다.  
  
 호출 하는 경우 **업데이트** 편집 된 레코드에 대 한:  
  
-   ODBC 드라이버가 지원는 **:: SQLSetPos** MFC ODBC API 함수는 함수를 사용 하 여 데이터 원본에서 레코드를 업데이트 합니다. 와 **:: SQLSetPos**, 드라이버 프로그램 편집 버퍼 두 개의 서로 다른 서버에 레코드를 업데이트 하는 서버에 있는 해당 레코드와 비교 합니다. 와 **:: SQLSetPos**, MFC를 업데이트할 수는 레코드 보다 효율적으로 생성 하 고 SQL 문을 처리 하는 없기 때문입니다.  
  
     -또는-  
  
-   경우 **:: SQLSetPos** 수 없습니다을 사용 하는 MFC에서 다음을 수행 합니다.  
  
    1.  변경 내용이 있는 경우 **업데이트** 없으며 0을 반환 합니다.  
  
    2.  변경 된 경우 **업데이트** SQL 생성 **업데이트** 문. 에 나열 된 열은 **업데이트** 변경 된 필드 데이터 멤버를 기준으로 하는 문입니다.  
  
    3.  **업데이트** 변경 내용을 커밋하면-실행는 **업데이트** 문-및 레코드는 변경 데이터 원본에 되지만 트랜잭션이 커밋되지 않음 경우 진행 중인 (참조 [트랜잭션:에서 트랜잭션 수행 레코드 집합 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) 트랜잭션이 업데이트에 미치는 영향에 대 한 정보에 대 한). ODBC 또한 변경 되는 레코드의 복사본을 유지 합니다.  
  
    4.  에 대 한 프로세스와는 달리 `AddNew`, **편집** 프로세스는 저장된 된 레코드를 복원 하지 않습니다. 편집 된 레코드 계속 현재 레코드로 적용 됩니다.  
  
    > [!CAUTION]
    >  호출 하 여 레코드 집합을 업데이트 하기 전에 **업데이트**, 하 여 포함 테이블의 기본 키를 구성 하는 모든 열 (또는 모든 열에는 모든 고유 인덱스에 테이블 또는 열을 고유 하 게 행을 식별) 합니다. 경우에 따라 프레임 워크 업데이트할 테이블의 레코드를 식별 하 레코드 집합에서 선택한 열만 사용할 수 있습니다. 필요한 모든 열이 없는 테이블의 여러 레코드를 업데이트할 수 있습니다. 호출 하는 경우 프레임 워크에서 예외를 throw 하는 경우에 **업데이트**합니다.  
  
    > [!TIP]
    >  호출 하는 경우 `AddNew` 또는 **편집** 호출 하기 전에 두 함수 호출 후 **업데이트**, 대체 새롭거나 편집 된 레코드에 저장된 된 레코드와 편집 버퍼는 새로 고쳐지고 진행 중입니다. 이 동작을 중단 하는 방법을 제공는 `AddNew` 또는 **편집** 하 고 새 시작: 진행률 레코드에 결함이 있는 인지를 확인 하는 경우 단순히 호출 **편집** 또는 `AddNew` 다시 합니다.  
  
##  <a name="_core_deleting_a_record"></a> 레코드 삭제  
 레코드 집합에서 레코드를 삭제 하면 스크롤하고 레코드로 호출 레코드 집합의 [삭제](../../mfc/reference/crecordset-class.md#delete) 멤버 함수입니다. 와 달리 `AddNew` 및 **편집**, **삭제** 에 대 한 일치 하는 호출 하지 않아도 **업데이트**합니다.  
  
 호출에 대 한 전제 조건으로 **삭제**레코드 집합을 업데이트할 수 있어야 하 고 레코드에 있어야 합니다. `CanUpdate`, `IsBOF`, `IsEOF`, 및 `IsDeleted` 멤버 함수를 사용 하 여 이러한 조건을 확인할 수 있습니다.  
  
 호출 하는 경우 **삭제**:  
  
-   ODBC 드라이버가 지원는 **:: SQLSetPos** MFC ODBC API 함수는 함수를 사용 하 여 데이터 원본에서 레코드를 삭제 합니다. 사용 하 여 **:: SQLSetPos** SQL을 사용 하 여 보다 일반적으로 더 효율적입니다.  
  
     -또는-  
  
-   경우 **:: SQLSetPos** 수 없습니다을 사용 하는 MFC에서 다음을 수행 합니다.  
  
    1.  편집 버퍼의 현재 레코드에서와 같이 백업 되지 않습니다 `AddNew` 및 **편집**합니다.  
  
    2.  **삭제** SQL 생성 **삭제** 레코드를 제거 하는 문입니다.  
  
         편집 버퍼의 현재 레코드에서와 같이 저장 되지 않습니다 `AddNew` 및 **편집**합니다.  
  
    3.  **삭제** 삭제 커밋합니다-실행는 **삭제** 문. 데이터 원본에 삭제 된 레코드가 표시 된 레코드가 스냅숏일 경우 ODBC의 경우.  
  
    4.  Null 및 레코드 집합의 필드 데이터 멤버 표시 되어 있지만 삭제 된 레코드의 값은 여전히는 레코드 집합의 필드 데이터 멤버 `IsDeleted` 멤버 함수는 0이 아닌 값을 반환 합니다.  
  
    > [!NOTE]
    >  레코드를 삭제 한 후 새 레코드의 데이터로 편집 버퍼 다시 다른 레코드로 스크롤하여 채워야 합니다. 호출 하면 오류가 발생 **삭제** 다시 또는 호출 하려면 **편집**합니다.  
  
 업데이트 작업에 사용 되는 SQL 문의 대 한 정보를 참조 하십시오. [SQL](../../data/odbc/sql.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 업데이트에 대해 자세히 알아보세요 (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)   
 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)