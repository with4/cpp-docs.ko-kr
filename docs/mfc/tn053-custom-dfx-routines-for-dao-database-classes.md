---
title: 'TN053: DAO에 대 한 사용자 지정 DFX 루틴 데이터베이스 클래스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dfx
dev_langs:
- C++
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60e42aedd406e7478db83ecddca7d8b82230abc5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951996"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO 데이터베이스 클래스에 대한 사용자 지정 DFX 루틴
> [!NOTE]
>  Visual c + + 환경 및 마법사 (DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다) 이지만 DAO을 지원 하지 않습니다. 사용 하는 것이 좋습니다 [OLE DB 템플릿](../data/oledb/ole-db-templates.md) 또는 [ODBC 및 MFC](../data/odbc/odbc-and-mfc.md) 새 프로젝트에 대 한 합니다. DAO는 기존 응용 프로그램 유지 관리만 사용할 수 있습니다.  
  
 이 기술 노트는 DAO 레코드 필드 교환 (DFX) 메커니즘을 설명합니다. DFX 루틴에서 일어나는 이해를 돕기 위한는 `DFX_Text` 함수 예를 들어 자세히 설명 되어 있습니다. 이 기술 노트는 정보의 추가 소스를으로 검사할 수 있습니다 코드 다른 개별 DFX 함수. 아마도 필요가 없습니다 사용자 지정 DFX 루틴 만큼 사용자 지정 RFX 루틴 (ODBC 데이터베이스 클래스와 함께 사용) 할 수 있습니다.  
  
 이 기술 노트 포함 되어 있습니다.  
  
-   DFX 개요  
  
- [예제](#_mfcnotes_tn053_examples) DAO 레코드 필드 교환 및 동적 바인딩을 사용 하 여  
  
- [DFX의 작동 원리](#_mfcnotes_tn053_how_dfx_works)  
  
- [사용자 지정 DFX 루틴에서 수행 하는 작업](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
- [DFX_Text의 세부 정보](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **DFX 개요**  
  
 DAO 레코드 필드 교환 (DFX) 메커니즘은 검색 하 고 데이터를 사용 하는 경우 업데이트 프로시저를 간소화 하는 데 사용 되는 `CDaoRecordset` 클래스입니다. 데이터 멤버를 사용 하는 프로세스를 간소화할는 `CDaoRecordset` 클래스입니다. 파생 하 여 `CDaoRecordset`, 테이블 또는 쿼리의 각 필드를 나타내는 파생 된 클래스에 데이터 멤버를 추가할 수 있습니다. 이 "정적 바인딩" 메커니즘은 간단 하지만 모든 응용 프로그램에 대 한 데이터 인출/update 메서드 만족할 수 없습니다. DFX 현재 레코드가 변경 될 때마다 모든 바인딩된 필드를 검색 합니다. 통화 변경 되 면 모든 필드를 페치 하지 않아도 되는 성능에 민감한 응용 프로그램을 개발 하는 경우 "동적 바인딩"을 통해 `CDaoRecordset::GetFieldValue` 및 `CDaoRecordset::SetFieldValue` 가 선택한 데이터 액세스 방법을 수 있습니다.  
  
> [!NOTE]
>  동적 바인딩 및 DFX 되지 않으므로 상호 배타적인 정적 및 동적 바인딩의 혼합 사용을 사용할 수 있습니다.  
  
## <a name="_mfcnotes_tn053_examples"></a> DAO 레코드 필드 교환만 예제 1-사용  
  
 (가정 `CDaoRecordset` -파생 클래스 `CMySet` 이미 열려)  
  
```  
// Add a new record to the customers table  
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```  
  
 **동적 바인딩만 예제 2 — 사용**  
  
 (사용 하 여 가정 `CDaoRecordset` 클래스 `rs`, 이미 열려 및)  
  
```  
// Add a new record to the customers table  
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default  
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```  
  
 **예제 3 — 사용의 DAO 레코드 필드 교환 및 동적 바인딩**  
  
 (직원 데이터를 찾아보는 것으로 가정 `CDaoRecordset`-파생 클래스 `emp`)  
  
```  
// Get the employee's data so that it can be displayed  
emp.MoveNext();

 
// If user wants to see employee's photograph,  
// fetch it  
COleVariant varPhoto;  
if (bSeePicture)  
    emp.GetFieldValue(_T("photo"),
    varPhoto);

 
// Display the data  
PopUpEmployeeData(emp.m_strFirstName,  
    emp.m_strLastName,
    varPhoto);
```  
  
## <a name="_mfcnotes_tn053_how_dfx_works"></a> DFX의 작동 원리  
  
 DFX 메커니즘은 MFC ODBC 클래스에서 사용 하는 레코드 필드 교환 (RFX) 메커니즘을 유사한 방식으로 작동 합니다. RFX와 DFX의 원칙 동일 하지만 내부 차이가 많습니다. DFX 함수 디자인 개별 DFX 루틴에서 거의 모든 코드 공유 되도록 했습니다. 만 가장 높은 수준 DFX에 몇 가지를 수행 하지 않습니다.  
  
-   DFX SQL 생성 **선택** 절 및 SQL **매개 변수** 필요한 경우 절.  
  
-   DFX 생성 DAO의에서 사용 하는 바인딩 구조의 `GetRows` 함수 (나중에 자세히).  
  
-   DFX (이중 버퍼링 사용 중인) 하는 경우에 커밋되지 않은 데이터 필드를 검색 하는 데 사용 되는 데이터 버퍼를 관리 합니다.  
  
-   DFX 관리는 **NULL** 및 **DIRTY** 상태 배열 및 업데이트에 필요한 경우 값을 설정 합니다.  
  
 메커니즘은는 DFX의 핵심은 `CDaoRecordset` 파생 클래스의 `DoFieldExchange` 함수입니다. 이 함수는 적절 한 작업 유형의 개별 DFX 함수에 대 한 호출을 전달합니다. 호출 하기 전에 `DoFieldExchange` 내부 MFC 함수 작업 유형을 설정 합니다. 다음 목록에는 다양 한 작업 유형에 대 한 간단한 설명을 표시 됩니다.  
  
|작업|설명|  
|---------------|-----------------|  
|`AddToParameterList`|빌드 매개 변수 절|  
|`AddToSelectList`|빌드 SELECT 절|  
|`BindField`|바인딩 구조를 설정합니다.|  
|`BindParam`|매개 변수 값 설정|  
|`Fixup`|NULL 상태 설정|  
|`AllocCache`|더티 검사에 대 한 캐시를 할당합니다.|  
|`StoreField`|에서는 현재 레코드를 캐시에 저장|  
|`LoadField`|멤버 값을 복원 캐시|  
|`FreeCache`|캐시를 해제합니다.|  
|`SetFieldNull`|집합 상태 및 NULL 값 필드|  
|`MarkForAddNew`|필드를 변경 하지 않은 경우 NULL 의사를 표시합니다.|  
|`MarkForEdit`|표시 필드 커밋되지 않은 경우 캐시에 일치 하지 않습니다.|  
|`SetDirtyField`|필드 있다고 표시의 값을 설정|  
  
 다음 섹션, 각 작업에 대 한 자세한 정보에 설명 되어 있습니다 `DFX_Text`합니다.  
  
 DAO 레코드 필드 교환 프로세스에 대 한 이해 하기 가장 중요 한 기능을 사용 하는 것은 `GetRows` 의 함수는 `CDaoRecordset` 개체입니다. DAO `GetRows` 함수는 여러 가지 방법으로 작업할 수 있습니다. 이 기술 노트만 간략하게 표시 `GetRows` 이므로이 기술 노트 범위를 벗어났습니다.  
  
 DAO `GetRows` 여러 가지 방법으로 작업할 수 있습니다.  
  
-   여러 레코드와 여러 데이터 필드를 한 번에 인출할 수 것입니다. 따라서 대형 데이터 구조와 각 필드에 대 한 적절 한 오프셋이 처리 하는 복잡 하지만 사용한 더 빠른 데이터 액세스에 대 한와 구조에서 데이터의 각 레코드에 있습니다. MFC는 메커니즘 인출이 여러 레코드의 활용 하지 않습니다.  
  
-   또 다른 방법은 `GetRows` 수 작업 데이터의 한 레코드의 각 필드의 검색된 된 데이터에 대 한 바인딩 주소를 지정 하는 프로그래머를 허용 하는 것입니다.  
  
-   DAO도 "으로 다시 호출할" 가변 길이 열에 대 한 호출자가 호출자가 메모리를 할당할 수 있도록 합니다. 이 두 번째 기능은 클래스의 멤버에는 데이터를 직접 저장할 수 있도록 뿐만 아니라 데이터의 복사본 수를 최소화 하는 이점이 (의 `CDaoRecordset` 파생 클래스). 이 두 번째 메커니즘은 MFC의 데이터 멤버에 바인딩하는 사용 하 여 메서드 `CDaoRecordset` 파생 클래스입니다.  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> 사용자 지정 DFX 루틴에서 수행 하는 작업  
 DFX 함수에서 구현 되는 가장 중요 한 작업 호출 하려면 필요한 데이터 구조를 설정 하는 기능 해야 합니다.이 설명에서 하는지가 명확 `GetRows`합니다. DFX 함수도 지원 해야 하는 다른 작업이 있지만 없음 중요 하거나 올바르게 준비로 복잡 한으로 여러 가지가 `GetRows` 호출 합니다.  
  
 DFX의 사용은 온라인 설명서에 설명 되어 있습니다. 기본적으로, 두 가지 요구 사항이 있습니다. 첫째, 멤버를에 추가 해야 합니다는 `CDaoRecordset` 각 바인딩된 필드 및 매개 변수 클래스를 파생 합니다. 다음 `CDaoRecordset::DoFieldExchange` 재정의 해야 합니다. 데이터 멤버의 형식이 중요 합니다. 최소한 해당 형식으로 변환할 수 또는 데이터베이스의 필드에서 데이터와 일치 해야 합니다. 예를 들어 정수 (long)를 같은 데이터베이스에 있는 숫자 필드 항상 텍스트로 변환 및 바인딩할 수는 `CString` 멤버 이지만 데이터베이스의 텍스트 필드 반드시 및 될 수 등 정수 (long) 숫자 표현으로 변환 긴 integ에 바인딩된 er 멤버입니다. DAO 및 Microsoft Jet 데이터베이스 엔진에서 변환 (아님 MFC)에 대 한 책임이 있습니다.  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX_Text의 세부 정보  
 앞에서 언급 한 DFX 작동 하는 방법을 설명 하는 가장 좋은 방법은 때 예를 통해 작동 하도록 합니다. 내부를 진행 하 고이 위해 `DFX_Text` DFX의 적어도 한 기본적인 이해를 제공 하기 위하여 매우 편리 하 게 작동 해야 합니다.  
  
 `AddToParameterList`  
 이 작업은 SQL 작성 **매개 변수** 절 ("`Parameters <param name>, <param type> ... ;`") Jet가 필요 합니다. 각 매개 변수는 명명 된 이며 (지정 된 대로 RFX 호출에) 입력 합니다. 함수를 참조 `CDaoFieldExchange::AppendParamType` 함수 개별 형식의 이름을 볼 수 있습니다. 경우 `DFX_Text`, 사용 되는 형식이 **텍스트**합니다.  
  
 `AddToSelectList`  
 Sql 문을 작성 **선택** 절. 추가 되는 단순히 DFX 호출에 의해 지정 된 열 이름으로 매우 단순 합니다 ("`SELECT <column name>, ...`").  
  
 `BindField`  
 작업 중 가장 복잡 합니다. 앞서 언급 했 듯이이 DAO 바인딩 구조의 사용한 `GetRows` 를 설정 합니다. 코드에서 볼 수 있듯이 `DFX_Text` 구조에 있는 정보의 종류를 사용 하는 DAO 형식 포함 (**DAO_CHAR** 또는 **DAO_WCHAR** 의 경우 `DFX_Text`). 또한 사용 하는 바인딩 유형은 설정 됩니다. 이전 단원에서 `GetRows` 설명만 간단 하 게 하지만 MFC에서 사용 되는 바인딩의 유형은 항상 직접 주소 바인딩을 설명 하는 데 충분 (**DAOBINDING_DIRECT**). 또한 가변 길이 열 바인딩에 대 한 (같은 `DFX_Text`) MFC 메모리 할당을 제어 하 고 올바른 길이의 주소를 지정할 수 있도록 콜백 바인딩이 사용 됩니다. 즉, MFC 등을 확인할 수 DAO 멤버 변수에 직접 바인딩할 수 있도록 하는 데이터를 삽입 하려면 "where"입니다. 바인딩 구조의 나머지는 메모리 할당 콜백 함수 및 열 바인딩 (열 이름으로 바인딩) 형식 주소 등 포함 됩니다.  
  
 `BindParam`  
 이 호출 하는 간단한 작업 `SetParamValue` 매개 변수 멤버에 지정 된 매개 변수 값을 사용 합니다.  
  
 `Fixup`  
 채웁니다는 **NULL** 각 필드에 대 한 상태입니다.  
  
 `SetFieldNull`  
 이 작업으로 각 필드의 상태를 표시만 **NULL** 구성원 변수 값을 설정 하 고 **PSEUDO_NULL**합니다.  
  
 `SetDirtyField`  
 호출 `SetFieldValue` 더티로 표시 된 각 필드에 대 한 합니다.  
  
 만 나머지 모든 작업 데이터 캐시를 사용 하 여 처리 합니다. 데이터 캐시는 특정 작업을 더 간단 하 게 하는 데 사용 되는 현재 레코드에 있는 데이터의 추가 버퍼입니다. 예를 들어, "더티" 필드를 자동으로 검색할 수 있습니다. 온라인 설명서에 설명 된 대로 것 해제할 수 있습니다 완전히 또는 필드 수준입니다. 버퍼의 구현에서 지도 사용합니다. 이 맵은 "바인딩된" 필드의 주소와이 데이터의 동적으로 할당 된 복사본을 일치 시키는 데 사용 됩니다 (또는 `CDaoRecordset` 데이터 멤버를 파생).  
  
 `AllocCache`  
 동적으로 캐시 된 필드 값을 할당 하 고 지도에 추가 합니다.  
  
 `FreeCache`  
 맵에서 제거 및 캐시 된 필드 값을 삭제 합니다.  
  
 `StoreField`  
 데이터 캐시에는 현재 필드 값을 복사합니다.  
  
 `LoadField`  
 필드 멤버에 캐시 된 값을 복사합니다.  
  
 `MarkForAddNew`  
 확인 하는 경우 현재 필드 값이 아닌**NULL** 하 고 필요한 경우 더티 표시 합니다.  
  
 `MarkForEdit`  
 데이터 캐시와 현재 필드 값과 비교 하 고 필요한 경우 커밋되지 않은 데이터를 표시 합니다.  
  
> [!TIP]
>  표준 데이터 형식에 대 한 기존 DFX 루틴에 사용자 지정 DFX 루틴을 모델링 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

