---
title: '레코드 필드 교환: RFX 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 296ae2e4f535e08924a77b8726b93778a6da5026
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-using-rfx"></a>레코드 필드 교환: RFX 사용
이 프레임 워크에서 수행 하는 작업을 기준으로 RFX 사용 수행할 설명 합니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다. [CRecordset](../../mfc/reference/crecordset-class.md) 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 다음 항목에서는 관련된 정보를 포함 합니다.  
  
-   [레코드 필드 교환: 마법사 코드 사용](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) RFX의 주요 구성 요소를 소개 하 고 코드에 설명 하는 MFC 응용 프로그램 마법사 및 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가 ](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX와 마법사 코드를 수정 하려는 방법을 지원 하기 위해 작성 합니다.  
  
-   [레코드 필드 교환: RFX 함수를 사용 하 여](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) RFX 함수에 대 한 호출을 작성에 설명 프로그램 `DoFieldExchange` 재정의 합니다.  
  
 다음 표에서 프레임 워크에서는을 수행 하는 데 기준으로 사용자의 역할을 보여 줍니다.  
  
### <a name="using-rfx-you-and-the-framework"></a>RFX 사용: 사용자 및 프레임 워크  
  
|사용자|프레임워크|  
|---------|-------------------|  

| 마법사와 함께 해당 레코드 집합 클래스를 선언 합니다. 필드 데이터 멤버의 이름 및 데이터 형식을 지정 합니다. | 마법사에서 파생 되는 `CRecordset` 클래스 및 쓰기는 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 을 재정의 각 필드 데이터 멤버에 대 한 호출 함수는 RFX를 포함 하 여. |  
| (선택 사항) 클래스에 필요한 매개 변수 데이터 멤버를 수동으로 추가 합니다. RFX 함수 호출에 수동으로 추가 `DoFieldExchange` 각 매개 변수 데이터 멤버에 대 한 호출을 추가 [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 매개 변수를 그룹에 대 한 매개 변수에서의 총 수를 지정 하 고 [m_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md). | |  
| (선택 사항) 필드 데이터 멤버에 수동으로 추가 열을 바인딩하십시오. 수동으로 늘리려면 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)합니다. 참조 [레코드 집합: 데이터 열 (ODBC)을 동적으로 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). | |  

| 레코드 집합 클래스의 개체를 생성 합니다. 개체를 사용 하기 전에 값을 설정 매개 변수의 데이터 멤버가 들어 있는 경우. | 효율성을 높이기 위해 프레임 워크를 워크가 미리 ODBC를 사용 하 여 매개 변수를 바인딩합니다. 매개 변수 값을 전달할 때 프레임 워크 데이터 원본에 전달 합니다. 정렬 및/또는 필터 문자열을 변경 하지 않은 재쿼리에 대 한 매개 변수 값만 전송 됩니다. |  
| 사용 하 여 recordset 개체 엽니다 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open). | 레코드 집합의 쿼리를 실행, 호출 및 레코드 집합의 필드 데이터 멤버에 열을 바인딩하는 `DoFieldExchange` 선택한 첫 번째 레코드와 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환 합니다. |  
| 사용 하 여 레코드 집합에서 스크롤 [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) 또는 메뉴 또는 도구 모음 명령입니다. | 호출 `DoFieldExchange` 새 현재 레코드에서 필드 데이터 멤버를 데이터를 전송 하도록 합니다. |  
| 추가, 업데이트 및 레코드를 삭제 합니다. | 호출 `DoFieldExchange` 데이터 원본에 데이터를 전송 하도록 합니다. |  
  
## <a name="see-also"></a>참고 항목  
 [레코드 필드 교환 (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [레코드 집합: 합계 및 다른 집계 결과 (ODBC) 구하기](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)   
 [매크로, 전역 함수 및 전역 변수](../../mfc/reference/mfc-macros-and-globals.md)

