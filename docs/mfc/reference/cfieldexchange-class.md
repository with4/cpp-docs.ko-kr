---
title: "CFieldExchange 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d20a89e48475a0226d76ac719459b1b99cc4e355
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cfieldexchange-class"></a>CFieldExchange 클래스
데이터베이스 클래스에서 사용되는 RFX(레코드 필드 교환) 및 대량 RFX(레코드 필드 교환) 루틴을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|업데이트 되는 필드의 형식에 적합 한 현재 작업 하는 경우 0이 아닌 반환 합니다.|  
|[CFieldExchange::SetFieldType](#setfieldtype)|레코드 집합 데이터 멤버의 유형을 지정-열 또는 매개 변수-다음에 호출할 때까지 다음 모든 RFX 함수 호출을 나타내는 `SetFieldType`합니다.|  
  
## <a name="remarks"></a>설명  
 `CFieldExchange`기본 클래스는 없습니다.  
  
 대량 행 페치를 구현 하는 경우 또는 사용자 지정 데이터 형식에 대 한 데이터 교환 루틴을 작성 하는 경우에이 클래스를 사용 하 여 그렇지 않으면 있습니다 사용 하지 않습니다 직접이 클래스. RFX 및 대량 RFX recordset 개체의 필드 데이터 멤버와 데이터 소스에서 현재 레코드에서 해당 필드 간에 데이터를 교환 합니다.  
  
> [!NOTE]
>  클래스를 사용 하 여 ODBC Open Database Connectivity () 클래스 아닌 개체 DAO (Data Access) 클래스와 함께 작업 하는 경우 [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) 대신 합니다. 자세한 내용은 문서 참조 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 A `CFieldExchange` 개체 컨텍스트 정보가 필요한 레코드 필드 교환 또는 되려면 대량 레코드 필드 교환에 대 한 배치를 제공 합니다. `CFieldExchange`개체는 현재 레코드의 필드에 다양 한 플래그를 설정 및 매개 변수 및 필드 데이터 멤버를 포함 하 여 작업의 수를 지원 합니다. 에 정의 된 형식의 레코드 집합 클래스 데이터 멤버에서 RFX 및 대량 RFX 작업이 수행 되는 `enum` **FieldType** 에서 `CFieldExchange`합니다. 가능한 **FieldType** 값은:  
  
- **CFieldExchange::outputColumn** 필드 데이터 멤버에 대 한 합니다.  
  
- **CFieldExchange::inputParam** 또는 **CFieldExchange::param** 입력된 매개 변수 데이터 멤버에 대 한 합니다.  
  
- **CFieldExchange::outputParam** 출력 매개 변수 데이터 멤버에 대 한 합니다.  
  
- **CFieldExchange::inoutParam** 입/출력 매개 변수 데이터 멤버에 대 한 합니다.  
  
 클래스의 멤버 함수 및 데이터 멤버의 대부분은 사용자 고유의 사용자 지정 RFX 루틴을 작성 하기 위한 제공 됩니다. 사용 하 여 `SetFieldType` 자주 있습니다. 자세한 내용은 문서를 참조 [Exchange RFX (레코드 필드)](../../data/odbc/record-field-exchange-rfx.md) 및 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다. 대량 행 페치에 대 한 정보에 대 한 문서를 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다. RFX 및 대량 RFX 전역 함수에 대 한 세부 정보를 참조 하십시오. [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md) 이 참조의 MFC 매크로 및 전역 섹션에 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CFieldExchange`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 사용자가 직접 RFX 함수를 작성 하는 경우 호출 `IsFieldType` 는 특정 필드 또는 매개 변수 데이터 멤버 형식에서 현재 작업을 수행할 수 있는지 여부를 확인 하 고 함수 시작 부분에 (한 **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, 또는 **CFieldExchange::inoutParam** ).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnField*  
 필드 또는 매개 변수 데이터 멤버의 일련 번호는이 매개 변수에서 반환 됩니다. 데이터 멤버의 순서에 해당 하는이 숫자는 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 경우 현재 필드 또는 매개 변수 형식에 현재 작업을 수행할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 RFX 함수 기존 모델을 따릅니다.  
  
##  <a name="setfieldtype"></a>CFieldExchange::SetFieldType  
 에 대 한 호출을 해야 `SetFieldType` 레코드 집합 클래스에 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 재정의 합니다.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFieldType`  
 값이는 **enum FieldType**에 선언 된 `CFieldExchange`, 다음 중 하나일 수 있습니다.  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>설명  
 필드 데이터 멤버에 대 한 호출 해야 `SetFieldType` 의 매개 변수와 함께 **CFieldExchange::outputColumn**와 RFX 또는 대량 RFX 함수를 호출 하 여 합니다. 대량 행 페치를 구현 하지 경우 classwizard 함께 사용이 배치 `SetFieldType` 의 필드 맵 부분를 대신 호출 `DoFieldExchange`합니다.  
  
 레코드 집합 클래스를 매개 변수화 하는 경우 호출 해야 `SetFieldType` 다시 모든 필드 맵 섹션 외부 뒤 RFX 호출 하 여 모든 매개 변수 데이터 멤버에 대 한 합니다. 각 형식 매개 변수 데이터 멤버의 있어야 자체 `SetFieldType` 호출 합니다. 다음 표에서 다양 한 값을 전달할 수 있습니다를 구별 `SetFieldType` 클래스의 매개 변수 데이터 멤버를 나타내는 데:  
  
|SetFieldType 매개 변수 값|형식의 매개 변수 데이터 멤버|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|입력된 매개 변수입니다. 레코드 집합의 쿼리 또는 저장된 프로시저에 전달 되는 값입니다.|  
|**CFieldExchange::param**|와 동일 **CFieldExchange::inputParam**합니다.|  
|**CFieldExchange::outputParam**|출력 매개 변수입니다. 레코드 집합의 저장된 프로시저의 반환 값입니다.|  
|**CFieldExchange::inoutParam**|입/출력 매개 변수입니다. 에 전달 되 고 레코드 집합의 저장된 프로시저에서 반환 하는 값입니다.|  
  
 일반적으로 필드 데이터 멤버 또는 매개 변수 데이터 멤버와 연결 된 RFX 함수 호출의 각 그룹 뒤에 야를 호출 하 여 `SetFieldType`합니다. `nFieldType` 각 매개 변수 `SetFieldType` 호출 다음에 나오는 RFX 함수 호출에 의해 표시 되는 데이터 멤버의 형식을 식별 하는 `SetFieldType` 호출 합니다.  
  
 출력 및 입/출력 매개 변수를 처리 하는 방법에 대 한 자세한 내용은 참조는 `CRecordset` 멤버 함수 [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)합니다. RFX 및 대량 RFX 함수에 대 한 자세한 내용은 항목을 참조 하십시오. [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)합니다. 대량 행 페치에 대 한 관련된 정보에 대 한 문서를 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
### <a name="example"></a>예  
 이 예제에 대 한 호출을 수행할 RFX 함수를 여러 번 호출 `SetFieldType`합니다. `SetFieldType` 통해서만 호출 되는 `pFX` 에 대 한 포인터는 `CFieldExchange` 개체입니다.  
  
 [!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)
