---
title: '레코드 필드 교환: RFX 작동 방식 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5eac97bb87103bd72dfd721515baf58324fc851f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-how-rfx-works"></a>레코드 필드 교환: RFX 작동 방식
이 항목에서는 RFX 프로세스에 설명 합니다. 고급 항목 포함:  
  
-   [RFX와 레코드 집합](#_core_rfx_and_the_recordset)  
  
-   [RFX 프로세스](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
##  <a name="_core_rfx_and_the_recordset"></a>RFX와 레코드 집합  
 한 레코드의 선택 된 열을 보유 하는 편집 버퍼를 구성 하는 레코드 집합 개체의 필드 데이터 멤버를 함께 사용 합니다. 레코드 집합은 처음 열리고 첫 번째 레코드 읽기를 RFX 바인딩 (연결 각) 선택 된 열을 해당 필드 데이터 멤버의 주소입니다. 레코드 집합에서 레코드를 업데이트 하는 경우 RFX SQL 보낼 ODBC API 함수를 호출 하는 **업데이트** 또는 **삽입** 드라이버는 문입니다. RFX 필드 데이터 멤버에 대 한 정보를 사용 하 여 작성 하는 열을 지정 합니다.  
  
 프레임 워크 백업 편집 버퍼 특정 단계에서 필요에 따라 해당 내용을 복원할 수 있도록 합니다. RFX 새 레코드를 추가 하기 전에 및 기존 레코드를 편집 하기 전에 편집 버퍼를 백업 합니다. 예를 들어, 일부 경우에 편집 버퍼 후 복원 된 **업데이트** 호출 다음 `AddNew`합니다. 사용자는 새로 변경된 된 편집 버퍼 버리는, 예를 들어를 호출 하기 전에 다른 레코드로 이동 하는 경우에 편집 버퍼 복원 되지 않습니다 **업데이트**합니다.  
  
 RFX 외에도 데이터 원본 및 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환 하는, 바인딩 매개 변수를 관리 합니다. 매개 변수 데이터 멤버의 순서 바인딩된 레코드 집합을 열면는 "?" SQL 문에 대 한 자리 표시자는 `CRecordset::Open` 생성 합니다. 자세한 내용은 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.  
  
 레코드 집합 클래스의 재정의 `DoFieldExchange` 양방향으로 데이터를 이동 합니다. 모든 작업을 수행 합니다. RFX (DDX) 하는 대화 상자 데이터 교환 처럼 클래스의 데이터 멤버에 대 한 정보를 필요합니다. 마법사의 특정 레코드 집합을 구현 하 여 필요한 정보를 제공 `DoFieldExchange` 를 기반으로 필드 데이터는 마법사를 사용 하 여 지정한 멤버 이름 및 데이터 형식입니다.  
  
##  <a name="_core_the_record_field_exchange_process"></a>레코드 필드 교환 프로세스  
 이 섹션에서는 레코드 집합 개체를 열 때 및 추가 하면 RFX 이벤트의 순서를 설명 하 고, 업데이트 및 레코드를 삭제 합니다. 테이블 [의 레코드 집합을 열 때 RFX 작업](#_core_sequence_of_rfx_operations_during_recordset_open) 테이블과 [스크롤할 때 RFX 작업](#_core_sequence_of_rfx_operations_during_scrolling) 이 항목의 처리로 프로세스를 표시 한 **이동**레코드 집합의 명령을 고 RFX 관리할 업데이트 합니다. 이러한 프로세스 중 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 다양 한 작업을 수행 하기 위해 호출 됩니다. **m_nOperation** 의 데이터 멤버는 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 어떤 작업이 요청 된 개체를 확인 합니다. 읽을 도움이 될 수 있습니다 [레코드 집합: 레코드 집합의 레코드 선택 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 및 [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 이 항목을 읽기 전에 합니다.  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>열 및 매개 변수의 RFX: 초기 바인딩  
 레코드 집합 개체를 호출 하는 경우 표시 된 순서 대로 다음 RFX 작업이 수행 [열려](../../mfc/reference/crecordset-class.md#open) 멤버 함수:  
  
-   프레임 워크를 호출 하는 레코드 집합에 매개 변수 데이터 멤버, `DoFieldExchange` 레코드 집합의 SQL 문 문자열의 매개 변수 자리 표시자는 매개 변수를 바인딩합니다. 각 자리 표시자에 대 한 매개 변수 값의 형식 종속 표현을 사용 하는 데이터에서 찾을 수는 **선택** 문. SQL 문의 준비 되었지만 실행 하기 전에 발생 합니다. 문 준비에 대 한 정보를 참조 하십시오.는 **:: SQLPrepare** 함수는 ODBC의 *Programmer's Reference*합니다.  
  
-   프레임 워크를 호출 하 여 `DoFieldExchange` 를 두 번째로 선택한 열의 값은 레코드 집합의 해당 필드 데이터 멤버에 바인딩할 합니다. 이 첫 번째 레코드의 열을 포함 하는 편집 버퍼 recordset 개체를 설정 합니다.  
  
-   레코드 집합은 SQL 문을 실행 하 고 데이터 원본 첫 번째 레코드를 선택 합니다. 레코드의 열은 레코드 집합의 필드 데이터 멤버에 로드 됩니다.  
  
 다음 표에서 레코드 집합을 열 때 RFX 작업 순서를 보여 줍니다.  
  
### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>레코드 집합 열기 중 RFX 작업 시퀀스  
  
|작업|DoFieldExchange 작업|데이터베이스/SQL 작업|  
|--------------------|-------------------------------|-----------------------------|  
|1. 레코드 집합을 엽니다.|||  
||2. SQL 문을 작성 합니다.||  
|||3. SQL을 보냅니다.|  
||4. 매개 변수 데이터 멤버에 바인딩하십시오.||  
||5. 필드 데이터 멤버 열에 바인딩하십시오.||  
|||6. ODBC에서 이동 하는 데이터를 채웁니다.|  
||7. C + +에 대 한 데이터를 수정 합니다.||  
  
 레코드 집합 ODBC의 준비 된 실행을 사용 하 여 동일한 SQL 문을 사용 하 여 빠르게 다시 쿼리할 수 있도록 합니다. 준비 된 실행에 대 한 자세한 내용은 ODBC SDK를 참조 하십시오. *Programmer's Reference* MSDN 라이브러리에서.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a>RFX: 스크롤  
 프레임 워크를 호출 하는 다른 한 레코드에서 스크롤할 때 `DoFieldExchange` 새 레코드에 대 한 값으로 필드 데이터 멤버에 이전에 저장 된 값을 교체할 수 있습니다.  
  
 다음 표에서 사용자가 레코드 간을 이동할 때 RFX 작업 순서를 보여 줍니다.  
  
### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a>스크롤 하는 동안 RFX 작업 시퀀스  
  
|작업|DoFieldExchange 작업|데이터베이스/SQL 작업|  
|--------------------|-------------------------------|-----------------------------|  
|1. 호출 `MoveNext` 또는 다른 이동 기능 중 하나입니다.|||  
|||2. ODBC에서 이동 하는 데이터를 채웁니다.|  
||3. C + +에 대 한 데이터를 수정 합니다.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: 새 레코드를 추가 및 기존 레코드 편집  
 새 레코드를 추가 하는 경우 레코드 집합에서 새 레코드의 콘텐츠를 작성 하는 편집 버퍼로 작동 합니다. 레코드를 추가할 때와 마찬가지로 레코드를 편집 해야 레코드 집합의 필드 데이터 멤버의 값을 변경 합니다. RFX 관점에서 시퀀스는 다음과 같습니다.  
  
1.  레코드 집합의를 호출 하 여 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 또는 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수로 인해 RFX 나중에 복원할 수 있도록 현재 편집 버퍼를 저장 합니다.  
  
2.  `AddNew`또는 **편집** RFX 변경 된 필드 데이터 멤버를 검색할 수 있도록 편집 버퍼에 필드를 준비 합니다.  
  
     새 레코드에 이전 값이 없는 새와 비교할 수 있기 때문에 `AddNew` 각 필드 데이터 멤버의 값을 설정 하는 **PSEUDO_NULL** 값입니다. 호출 하는 경우에 이후 **업데이트**, RFX와 각 데이터 멤버의 값을 비교는 **PSEUDO_NULL** 값입니다. 차이점이 있을 경우 데이터 멤버가 설정 되었습니다. (**PSEUDO_NULL** Null 값이 true 인 레코드 열과 동일 하지 않으며 아닙니다 둘 중 하나를 c + + 동일 **NULL**.)  
  
     와 달리는 **업데이트** 에 대 한 호출 `AddNew`, **업데이트** 에 대 한 호출 **편집** 를사용하여보다는이전에저장된값으로업데이트된값을비교하여**PSEUDO_NULL**합니다. 차이점은 `AddNew` 값이 없는 이전에 저장 된 비교 합니다.  
  
3.  직접 편집 하려면 해당 값 또는에 새 레코드를 채우려는 필드 데이터 멤버의 값을 설정 합니다. 호출을 포함할 수 있습니다이 `SetFieldNull`합니다.  
  
4.  호출 하 여 [업데이트](../../mfc/reference/crecordset-class.md#update) 2 단계에 설명 된 대로 변경 된 필드 데이터 멤버에 대 한 확인 (표를 참조 [스크롤할 때 RFX 작업](#_core_sequence_of_rfx_operations_during_scrolling)). None 변경 되 면 **업데이트** 0을 반환 합니다. 일부 필드 데이터 멤버 변경 되 면 **업데이트** 준비 하 고 SQL 실행 **삽입** 레코드의 업데이트 된 모든 필드에 대 한 값을 포함 하는 문입니다.  
  
5.  에 대 한 `AddNew`, **업데이트** 이전의 현재 레코드의 이전에 저장 된 값을 복원 하 여 결론을 내립니다는 `AddNew` 호출 합니다. 에 대 한 **편집**을 편집한 경우에 새 값이 그대로 남아 있습니다.  
  
 다음 표에서 새 레코드를 추가 하거나 기존 레코드를 편집할 때 RFX 작업 순서를 보여 줍니다.  
  
### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew 및 편집 하는 동안 RFX 작업 시퀀스  
  
|작업|DoFieldExchange 작업|데이터베이스/SQL 작업|  
|--------------------|-------------------------------|-----------------------------|  
|1. 호출 `AddNew` 또는 **편집**합니다.|||  
||2. 편집 버퍼를 백업 합니다.||  
||3. 에 대 한 `AddNew`, 필드 데이터 멤버를 "정리"으로 표시 데이터 요소 및 Null입니다.||  
|4. 레코드 집합 필드 데이터 멤버에 값을 할당 합니다.|||  
|5. 호출 **업데이트**합니다.|||  
||6. 변경 된 필드를 확인 합니다.||  
||7. SQL 빌드 **삽입** 문을 `AddNew` 또는 **업데이트** 문을 **편집**합니다.||  
|||8. SQL을 보냅니다.|  
||9. 에 대 한 `AddNew`,-백업 된 내용으로 편집 버퍼를 복원 합니다. 에 대 한 **편집**, 백업을 삭제 합니다.||  
  
### <a name="rfx-deleting-existing-records"></a>RFX: 기존 레코드를 삭제합니다.  
 레코드를 삭제 하면 RFX 모든 필드를 설정 **NULL** 하는 레코드가 삭제 되 고 연장해 해야 합니다. 다른 RFX 시퀀스 정보가 필요가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 필드 교환 (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [매크로, 전역 함수 및 전역 변수](../../mfc/reference/mfc-macros-and-globals.md)  
 [CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)