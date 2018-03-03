---
title: "TN043: RFX 루틴 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RFX
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 19bb44653c03505d954318a01a6e34c1a297dba7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn043-rfx-routines"></a>TN043: RFX 루틴
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 레코드 필드 교환 (RFX) 아키텍처를 설명합니다. 또한 작성 하는 방법을 설명는 **RFX_** 프로시저입니다.  
  
## <a name="overview-of-record-field-exchange"></a>레코드 필드 교환 개요  
 모든 레코드 집합 필드 함수는 c + + 코드도 수행 됩니다. 특별 한 리소스 또는 매직 매크로 없는 합니다. 메커니즘의 핵심은 모든 레코드 집합 파생된 클래스에서 재정의 되어야 하는 가상 함수입니다. 항상이 폼에서 발견 되었습니다.  
  
```  
void CMySet::DoFieldExchange(CFieldExchange* pFX)  
{ *//{{AFX_FIELD_MAP(CMySet)  
 <recordset exchange field type call>  
 <recordset exchange function call> *//}}AFX_FIELD_MAP  
}  
```  
  
 특수 형식 AFX 주석을 사용할 경우 클래스 마법사를 찾아이 함수 내에서 코드를 편집 합니다. 클래스 마법사와 호환 되지 않는 코드가 특수 형식 주석 밖에 배치 되어야 합니다.  
  
 위의 예에서 < recordset_exchange_field_type_call >는 형태로 표현:  
  
```  
pFX->SetFieldType(CFieldExchange::outputColumn);
```  
  
 그리고 < recordset_exchange_function_call > 양식에서:  
  
```  
RFX_Custom(pFX, "Col2",
    m_Col2);
```  
  
 대부분 **RFX_** 함수 3 개 인수, 위와 같이 되지만 일부 (예: `RFX_Text` 및 `RFX_Binary`) 추가로 선택적 인수를 사용 합니다.  
  
 둘 이상의 **RFX_** 각각에 포함 될 수 있습니다 `DoDataExchange` 함수입니다.  
  
 MFC와 함께 제공 하는 모든 레코드 필드 교환 루틴의 목록에 대 한 ' afxdb.h'를 참조 하십시오.  
  
 레코드 집합 필드 호출은 메모리 위치 (일반적으로 데이터 멤버)를 등록에 대 한 필드 데이터를 저장 하는 방법 한 **CMySet** 클래스입니다.  
  
## <a name="notes"></a>노트  
 레코드 집합 필드 함수는에 작동 하도록 설계 되었습니다는 `CRecordset` 클래스입니다. 다른 MFC 클래스에서 일반적으로 사용할 수는 없습니다.  
  
 데이터의 초기 값이 블록에 일반적으로 표준 c + + 생성자에서 설정 됩니다 `//{{AFX_FIELD_INIT(CMylSet)` 및 `//}}AFX_FIELD_INIT` 메모 합니다.  
  
 각 **RFX_** 함수 보관 필드를 편집 하는 준비 과정에서 필드를 반환 하는 필드의 더티 상태에 이르기까지 다양 한 작업을 지원 해야 합니다.  
  
 각 함수를 호출 하는 `DoFieldExchange` (예를 들어 `SetFieldNull`, `IsFieldDirty`)를 호출 하는 주변 초기화가 `DoFieldExchange`합니다.  
  
## <a name="how-does-it-work"></a>어떻게 작동 합니까  
 레코드 필드 교환을 사용 하려면 다음을 이해 하 고 필요가 없습니다. 그러나 이해 데 도움이 됩니다 원리를 자세히 파악할수록이 과정에 exchange 프로시저를 직접 작성 합니다.  
  
 `DoFieldExchange` 멤버 함수는 것과 마찬가지로 `Serialize` 멤버 함수-는 수집 또는/클래스에서 멤버 데이터에서 / (에 ODBC 쿼리 결과에서이 사례 열) 된 외부 형식에서 데이터를 설정 해야 합니다. `pFX` 매개 변수 데이터 교환을 수행 하는 데 컨텍스트 이며는 비슷합니다는 `CArchive` 매개 변수를 `CObject::Serialize`합니다. `pFX` (한 `CFieldExchange` 개체)에 작업 표시기 비슷합니다를 있지만 일반화 한는 `CArchive` 방향 플래그입니다. RFX 함수는 다음 작업을 지원 해야 할 수 있습니다.  
  
- **BindParam** -ODBC 매개 변수 데이터를 검색 해야 하는 표시  
  
- **BindFieldToColumn** -여기서 ODBC 해야 검색/입금 outputColumn 데이터 표시  
  
- **픽스업** -설정 **CString/CByteArray** 길이, NULL 상태 비트 설정  
  
- **MarkForAddNew** — 표시 값 AddNew를 호출 하는 이후 변경 된 경우 커밋되지 않음  
  
- **MarkForUpdate** — 표시 값 편집 호출 이후 변경 된 경우 커밋되지 않음  
  
- **이름** -더티로 표시 된 필드에 대 한 필드 이름을 추가 합니다.  
  
- **NameValue** -추가 "\<열 이름 > =" 더티로 표시 된 필드에 대 한  
  
- **값** -추가 ""와 같은 다음 구분 기호를 ',' 또는 ' '  
  
- `SetFieldDirty`--상태 비트 더티 (즉, 변경된) 필드를 설정 하는 중  
  
- `SetFieldNull`-필드에 null 값을 나타내는 상태 비트를 설정 합니다.  
  
- `IsFieldDirty`-더티 상태 비트의 값을 반환 합니다.  
  
- `IsFieldNull`-Null 상태 비트의 값을 반환 합니다.  
  
- `IsFieldNullable`-필드는 NULL 값을 가질 수 있는 경우 TRUE를 반환  
  
- **StoreField** -보관 필드 값  
  
- **LoadField** -다시 로드 보관 필드 값  
  
- **GetFieldInfoValue** -필드에 대 한 일반 정보 반환  
  
- **GetFieldInfoOrdinal** -필드에 대 한 일반 정보 반환  
  
## <a name="user-extensions"></a>사용자 확장  
 기본 RFX 메커니즘을 확장 하는 방법은 여러 가지가 있습니다. 다음과 같은 작업을 수행할 수 있습니다.  
  
-   새 데이터 형식을 추가 합니다. 예:  
  
 ```  
    CBookmark 
 ```  
  
-   새 exchange 프로시저 (RFX_)를 추가 합니다.  
  
 ```  
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
    const char *szName,  
    BIGINT& value);

 ```  
  
-   있어야는 `DoFieldExchange` 멤버 함수는 조건에 따라 추가 RFX 호출 또는 다른 올바른 c + + 문을 포함 합니다.  
  
 ```  
    while (posExtraFields != NULL)  
 {  
    RFX_Text(pFX,
    m_listName.GetNext(posExtraFields),   
    m_listValue.GetNext(posExtraValues));

 }  
 ```  
  
> [!NOTE]
>  이러한 코드 classwizard 함께 사용 하 여 편집할 수 없습니다 및 특수 형식 주석 외에 사용 해야 합니다.  
  
## <a name="writing-a-custom-rfx"></a>사용자 지정 RFX 작성  
 사용자 고유의 사용자 지정 RFX 함수를 작성 하려면 기존 RFX 함수 복사한 용도 맞게 수정할 것이 좋습니다. 복사할 오른쪽 RFX을 선택 하면 작업 훨씬 쉽게 수 있습니다. 일부 RFX 함수 복사을 결정할 때 고려해 야 하는 일부 고유 속성을 갖고 있습니다.  
  
 **RFX_Long 및 RFX_Int**:  
 이것은 가장 간단한 RFX 함수입니다. 데이터 값에는 특별 한 해석이 필요 하 고 데이터 크기는 고정 됩니다.  
  
 **RFX_Single 및 RFX_Double**:  
 RFX_Long 및 RFX_Int 위의 마찬가지로 이러한 함수는 간단 되며 정확해 기본 구현 광범위 하 게 사용 합니다. 그러나 부동 소수점 라이브러리는 명시적으로 참조 해야 하는 경우에 런타임을 로드를 사용 하도록 설정 하려면 dbrfx.cpp, 대신 dbflt.cpp에 저장 됩니다.  
  
 **RFX_Text 및 RFX_Binary**:  
 이 두 기능 문자열/이진 정보를 보관 하는 정적 버퍼를 미리 할당 하 고 등록 & 값 대신 ODBC SQLBindCol에 이러한 버퍼를 등록 해야 합니다. 이 때문에 이러한 두 함수를 사용 하면 특별 한 경우 코드의 많을 합니다.  
  
 `RFX_Date`:  
 ODBC는 고유한 TIMESTAMP_STRUCT 데이터 구조에 날짜와 시간 정보를 반환합니다. 이 함수는 "프록시"는 TIMESTAMP_STRUCT 날짜 시간 데이터 보내기 및 받기에 대 한 동적으로 할당 합니다. 다양 한 작업은 c + + 사이의 날짜 및 시간 정보를 전송 해야 `CTime` 개체 및 TIMESTAMP_STRUCT 프록시입니다. 이 인해 복잡이 함수를 보이고 이지만 데이터 전송에 대 한 프록시를 사용 하는 방법의 좋은 예입니다.  
  
 `RFX_LongBinary`:  
 RFX 함수를 데이터를 보내고 받는 열 바인딩을 사용 하지 않는 유일한 클래스 라이브러리입니다. 이 함수 BindFieldToColumn 작업을 무시 하 고 수정 작업 중 들어오는 SQL_LONGVARCHAR 또는 SQL_LONGVARBINARY 데이터를 저장 하려면 저장소를 할당 합니다. 다음을 할당 된 저장소에 값을 검색 하는 SQLGetData 호출을 수행 합니다. 데이터 값 (예: NameValue 및 값 작업) 데이터 소스에 다시 보낼 준비를 하는 경우이 함수는 ODBC의 DATA_AT_EXEC 기능을 사용 합니다. 참조 [기술 참고 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) SQL_LONGVARBINARY 및 SQL_LONGVARCHARs 작업에 대 한 자세한 내용은 합니다.  
  
 직접 작성 하는 경우 **RFX_** 함수를 종종 수 있습니다 사용할 **CFieldExchange::Default** 지정 된 작업을 구현 하 합니다. 작업에 대 한 기본 구현의 확인 합니다. 작성 해야 할 동작을 수행 하는 경우 프로그램 **RFX_** 함수를 위임할 수 있습니다는 **CFieldExchange::Default 합니다.** 호출의 예를 확인할 수 **CFieldExchange::Default** dbrfx.cpp에  
  
 호출 해야 `IsFieldType` RFX 함수 및 FALSE를 반환 하는 경우에 즉시 반환의 시작 부분에 있습니다. 이 메커니즘은 매개 변수 작업에 대해 수행 됨을 유지 **outputColumns**, 그 반대의 (호출 처럼 **BindParam** 에 **outputColumn**). 또한 `IsFieldType` 자동으로 한 추적 수가 **outputColumns** (`m_nFields`) 및 매개 변수 (`m_nParams`).  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

