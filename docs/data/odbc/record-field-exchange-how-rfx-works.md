---
title: "레코드 필드 교환: RFX 작동 방식 | Microsoft Docs"
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
  - "데이터 바인딩[C++], DFX"
  - "ODBC[C++], RFX"
  - "레코드 편집[C++], RFX 사용"
  - "RFX(ODBC)[C++], 필드 및 매개 변수 바인딩"
  - "RFX(ODBC)[C++], 레코드 집합의 데이터 업데이트"
  - "스크롤[C++]"
  - "스크롤[C++], RFX"
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 필드 교환: RFX 작동 방식
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 RFX 프로세스에 대해 설명합니다.  여기에서 다루는 내용은 다음과 같은 전문적인 내용입니다.  
  
-   [RFX 및 레코드 집합](#_core_rfx_and_the_recordset)  
  
-   [RFX 프로세스](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 클래스에 적용됩니다.  대량 행 페치를 사용하는 경우 Bulk RFX\(대량 레코드 필드 교환\)가 구현됩니다.  Bulk RFX는 RFX와 비슷합니다.  차이점을 이해하려면 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
##  <a name="_core_rfx_and_the_recordset"></a> RFX 및 레코드 집합  
 전체적으로 볼 때 레코드 집합 개체의 필드 데이터 멤버들은 특정 레코드에서 선택된 열을 보유하는 편집 버퍼를 구성합니다.  레코드 집합이 처음 열리고 첫 번째 레코드를 읽기 시작하면 RFX는 선택된 각 열을 해당 필드 데이터 멤버의 주소로 바인딩\(연결\)합니다.  레코드 집합에서 레코드가 업데이트되면 RFX는 ODBC API 함수를 호출하여 SQL **UPDATE** 또는 **INSERT** 문을 드라이버로 보냅니다.  RFX는 필드 데이터 멤버에 대한 자체 정보를 사용하여 쓰여질 열을 지정합니다.  
  
 프레임워크는 필요한 경우 버퍼의 내용을 복원할 수 있도록 특정 단계에서 편집 버퍼를 백업합니다.  또한 RFX는 새 레코드를 추가하기 전과 기존 레코드를 편집하기 전에 편집 버퍼를 백업합니다.  **Update**를 호출한 다음 `AddNew`를 호출하는 경우 등에는 편집 버퍼를 복원합니다.  사용자가 새로 변경된 편집 버퍼를 버리는 경우\(예: **Update**를 호출하기 전에 다른 레코드로 이동하는 경우\)에는 편집 버퍼가 복원되지 않습니다.  
  
 RFX는 데이터 소스와 레코드 집합의 필드 데이터 멤버 간의 데이터 교환뿐만 아니라 매개 변수 바인딩도 관리합니다.  레코드 집합이 열릴 때 모든 매개 변수 데이터 멤버는 `CRecordset::Open`이 생성한 SQL 문에 있는 자리 표시자 "?"의 순서대로 바인딩됩니다.  자세한 내용은 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.  
  
 레코드 집합 클래스의 `DoFieldExchange` 재정의는 양방향 데이터 이동과 관련된 모든 작업을 수행합니다.  DDX\(대화 상자 데이터 교환\)처럼 RFX도 클래스의 데이터 멤버에 대한 정보가 필요합니다.  마법사는 사용자가 마법사를 사용하여 지정한 필드 데이터 멤버 이름 및 데이터 형식에 따라 `DoFieldExchange`의 특정 레코드 집합을 구현하여 필요한 정보를 제공합니다.  
  
##  <a name="_core_the_record_field_exchange_process"></a> 레코드 필드 교환 프로세스  
 이 절에서는 레코드 집합 개체가 열릴 때와 사용자가 레코드 집합을 추가, 업데이트 및 삭제할 때 발생하는 RFX 이벤트 시퀀스에 대해 설명합니다.  이 항목의 [레코드 집합을 열 때 수행되는 RFX 작업](#_core_sequence_of_rfx_operations_during_recordset_open) 표와 [스크롤할 때 수행되는 RFX 작업](#_core_sequence_of_rfx_operations_during_scrolling) 표에서는 RFX가 레코드 집합의 **Move** 명령을 처리하고 RFX가 업데이트를 관리할 때의 프로세스를 보여 줍니다.  이 프로세스 중에 다른 여러 연산을 수행하기 위해 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)가 호출됩니다.  [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체의 **m\_nOperation** 데이터 멤버는 어떤 작업이 요청되었는지 확인합니다.  이 항목을 읽기 전에 [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 및 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 읽는 것이 좋습니다.  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX: 열과 매개 변수의 초기 바인딩  
 레코드 집합 개체의 [Open](../Topic/CRecordset::Open.md) 멤버 함수를 호출할 때 표시된 순서대로 다음 RFX 작업이 수행됩니다.  
  
-   레코드 집합에 매개 변수 데이터 멤버가 있으면 프레임워크가 `DoFieldExchange`를 호출하여 매개 변수를 레코드 집합의 SQL 문 문자열에 있는 매개 변수 자리 표시자에 바인딩합니다.  **SELECT** 문에 있는 각 자리 표시자에 대한 매개 변수 값은 데이터 형식에 따라 서로 다르게 표시됩니다.  이 작업은 SQL 문이 준비되어 있지만 아직 실행되기 전일 때 일어납니다.  문 준비에 대한 자세한 내용은 ODBC *Programmer's Reference*의 **::SQLPrepare** 함수를 참조하십시오.  
  
-   프레임워크가 `DoFieldExchange`를 두 번째로 호출하여 선택한 열의 값을 레코드 집합의 해당 필드 데이터 멤버에 바인딩합니다.  이렇게 하면 레코드 집합 개체가 첫 번째 레코드의 열을 포함하는 편집 버퍼로 구성됩니다.  
  
-   레코드 집합이 SQL 문을 실행하고 데이터 소스는 첫 번째 레코드를 선택합니다.  이렇게 하면 레코드의 열이 레코드 집합의 필드 데이터 멤버로 로드됩니다.  
  
 다음 표는 레코드 집합을 열 때 수행되는 RFX 작업을 순서대로 보여 줍니다.  
  
### 레코드 집합을 열 때 수행되는 RFX 작업  
  
|작업|DoFieldExchange 작업|데이터베이스\/SQL 작업|  
|--------|------------------------|--------------------|  
|1.  레코드 집합을 엽니다.|||  
||2.  SQL 문을 빌드합니다.||  
|||3.  SQL을 보냅니다.|  
||4.  매개 변수 데이터 멤버를 바인딩합니다.||  
||5.  필드 데이터 멤버를 열에 바인딩합니다.||  
|||6.  ODBC가 이동을 실행하고 데이터가 채워집니다.|  
||7.  C\+\+용 데이터를 수정합니다.||  
  
 레코드 집합은 ODBC의 준비된 실행을 사용함으로써 동일한 SQL 문을 사용하여 빠르게 다시 쿼리할 수 있도록 합니다.  준비된 실행에 대한 자세한 내용은 MSDN Library의 ODBC SDK *Programmer's Reference*를 참조하십시오.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX: 스크롤  
 사용자가 한 레코드에서 다른 레코드로 스크롤하면 프레임워크는 `DoFieldExchange`를 호출하여 이전에 필드 데이터 멤버에 저장된 값을 새 레코드의 값으로 바꿉니다.  
  
 다음 표는 사용자가 레코드를 스크롤할 때 수행되는 RFX 작업을 순서대로 보여 줍니다.  
  
### 스크롤할 때 수행되는 RFX 작업  
  
|작업|DoFieldExchange 작업|데이터베이스\/SQL 작업|  
|--------|------------------------|--------------------|  
|1.  `MoveNext`를 호출하거나 다른 Move 함수 중 하나를 호출합니다.|||  
|||2.  ODBC가 이동을 실행하고 데이터가 채워집니다.|  
||3.  C\+\+용 데이터를 수정합니다.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: 새 레코드 추가 및 기존 레코드 편집  
 새 레코드를 추가하면 레코드 집합이 편집 버퍼로 동작하여 새 레코드의 내용을 빌드합니다.  레코드를 추가할 때와 마찬가지로 레코드를 편집할 때도 레코드 집합의 필드 데이터 멤버 값이 변경됩니다.  RFX 측면에서 작업 순서는 다음과 같습니다.  
  
1.  사용자가 레코드 집합의 [AddNew](../Topic/CRecordset::AddNew.md) 또는 [Edit](../Topic/CRecordset::Edit.md) 멤버 함수를 호출하면 RFX가 현재 편집 버퍼 내용을 나중에 복원할 수 있도록 저장합니다.  
  
2.  `AddNew` 또는 **Edit**는 RFX가 변경된 필드 데이터 멤버를 감지할 수 있도록 편집 버퍼에 필드를 준비합니다.  
  
     새 레코드에는 새 값과 비교할 수 있는 이전의 값이 없기 때문에 `AddNew`는 각 필드 데이터 멤버의 값을 **PSEUDO\_NULL** 값으로 설정합니다.  나중에 사용자가 **Update**를 호출하면 RFX는 각 데이터 멤버의 값을 **PSEUDO\_NULL** 값과 비교합니다.  비교한 값에 차이가 있으면 데이터 멤버가 설정되어 있는 경우입니다. **PSEUDO\_NULL**은 레코드 열에 들어가는 실제 Null 값과 다르며, 둘 다 C\+\+에서 사용하는 **NULL**과도 다릅니다.  
  
     **Update**를 호출하여 `AddNew`를 수행하는 것과 달리 **Update**를 호출하여 **Edit**를 수행하면 **PSEUDO\_NULL**을 사용하는 것이 아니라 업데이트된 값을 이전에 저장된 값과 비교합니다.  이 두 가지는 `AddNew`의 경우 비교에 필요한 이전에 저장된 값을 가지고 있지 않다는 점에서 차이가 있습니다.  
  
3.  값을 편집하거나 새 레코드에 채우려는 필드 데이터 멤버의 값을 직접 설정합니다.  여기에는 `SetFieldNull` 호출도 포함될 수 있습니다.  
  
4.  2단계에서 설명한 것처럼 [Update](../Topic/CRecordset::Update.md)를 호출하여 변경된 필드 데이터 멤버가 있는지 검사합니다\([스크롤할 때 수행되는 RFX 작업](#_core_sequence_of_rfx_operations_during_scrolling) 표 참조\).  변경된 내용이 없는 경우 **Update**는 0을 반환합니다.  일부 필드 데이터 멤버가 변경된 경우 **Update**는 해당 레코드의 모든 업데이트된 필드에 대한 값을 포함하는 SQL **INSERT** 문을 준비하고 실행합니다.  
  
5.  `AddNew`의 경우 `AddNew`를 호출하기 전에 있던 레코드의 이전 저장 값을 복원함으로써 **Update**가 종료됩니다.  **Edit**의 경우에는 새로 편집된 값이 그대로 남아 있습니다.  
  
 다음 표는 새 레코드를 추가하거나 기존의 레코드를 편집할 때 수행되는 RFX 작업을 순서대로 보여 줍니다.  
  
### 새 레코드 추가 및 기존 레코드 편집하는 동안 수행되는 RFX 작업  
  
|작업|DoFieldExchange 작업|데이터베이스\/SQL 작업|  
|--------|------------------------|--------------------|  
|1.  `AddNew` 또는 **Edit**를 호출합니다.|||  
||2.  편집 버퍼의 내용을 백업합니다.||  
||3.  `AddNew`의 경우 필드 데이터 멤버를 비우고 Null로 표시합니다.||  
|4.  레코드 집합 필드 데이터 멤버에 값을 할당합니다.|||  
|5.  **Update**를 호출합니다.|||  
||6.  변경된 필드가 있는지 검사합니다.||  
||7.  SQL **INSERT** 문\(`AddNew`의 경우\) 또는 **UPDATE** 문\(**Edit**의 경우\)을 빌드합니다.||  
|||8.  SQL을 보냅니다.|  
||9.  `AddNew`의 경우 편집 버퍼를 백업된 내용으로 복원합니다.  **Edit**의 경우 백업을 삭제합니다.||  
  
### RFX: 기존 레코드 삭제  
 사용자가 레코드를 삭제하면 RFX는 모든 필드를 **NULL**로 설정하여 레코드가 삭제되었으며 이를 해당 필드에서 제거해야 한다는 것을 알려 줍니다.  다른 RFX 시퀀스 정보는 필요하지 않습니다.  
  
## 참고 항목  
 [RFX](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [매크로, 전역 함수 및 전역 변수](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)