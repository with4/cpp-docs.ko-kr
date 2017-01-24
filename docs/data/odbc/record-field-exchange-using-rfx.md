---
title: "레코드 필드 교환: RFX 사용 | Microsoft Docs"
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
  - "RFX(ODBC), 구현"
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 필드 교환: RFX 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 RFX를 사용하기 위해 사용자가 수행해야 하는 작업을 프레임워크 작업과 연관지어 설명합니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 [CRecordset](../../mfc/reference/crecordset-class.md)에서 파생된 클래스에 적용됩니다.  대량 행 페치를 사용하는 경우 Bulk RFX\(대량 레코드 필드 교환\)가 구현됩니다.  Bulk RFX는 RFX와 비슷합니다.  차이점을 이해하려면 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 다음 항목에는 관련 정보가 들어 있습니다.  
  
-   [레코드 필드 교환: 마법사 코드 사용](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) \- RFX의 주요 구성 요소를 소개하고, RFX를 지원하기 위해 MFC 응용 프로그램 마법사 및 **클래스 추가**\([MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)에서 설명\)에서 작성하는 코드, 마법사 코드 수정 방법 등을 설명합니다.  
  
-   [레코드 필드 교환: RFX 함수 사용](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) \- `DoFieldExchange` 재정의에서 RFX 함수에 대한 호출을 작성하는 방법을 설명합니다.  
  
 다음 표는 프레임워크에서 자동으로 수행하는 작업과 연관된 사용자의 역할을 보여 줍니다.  
  
### RFX 사용: 사용자 및 프레임워크  
  
|사용자|프레임워크|  
|---------|-----------|  
|마법사를 사용하여 레코드 집합 클래스를 선언합니다.  필드 데이터 멤버의 이름 및 데이터 형식을 지정합니다.|마법사가 `CRecordset` 클래스를 파생시키고 각 필드 데이터 멤버에 대한 RFX 함수 호출을 포함하여 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)를 자동으로 재정의합니다.|  
|\(선택 사항\)필요한 매개 변수 데이터 멤버를 클래스에 직접 추가합니다.  각 매개 변수 데이터 멤버에 대해 `DoFieldExchange`에 대한 RFX 함수를 수동으로 추가하고, 매개 변수 그룹에 대해 [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) 호출을 추가하고, [m\_nParams](../Topic/CRecordset::m_nParams.md)에 전체 매개 변수 개수를 지정합니다.  [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.||  
|\(선택 사항\) 필드 데이터 멤버에 추가 열을 직접 바인딩합니다.  [CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)를 직접 증가시킵니다.  [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.||  
|레코드 집합 클래스의 개체를 생성합니다.  개체를 사용하기 전에 필요하면 해당 매개 변수 데이터 멤버의 값을 설정합니다.|효율성을 위해, 프레임워크가 ODBC를 사용하여 매개 변수를 미리 바인딩합니다.  사용자가 매개 변수 값을 전달하면 프레임워크가 이 값을 데이터 소스에 전달합니다.  정렬 및\/또는 필터 문자열이 변경되지 않은 경우 매개 변수 값만 재쿼리하기 위해 보내집니다.|  
|[CRecordset::Open](../Topic/CRecordset::Open.md)을 사용하여 레코드 집합 개체를 엽니다.|레코드 집합의 쿼리를 실행하고 열을 레코드 집합의 필드 데이터 멤버로 바인딩한 다음 `DoFieldExchange`를 호출하여 처음 선택한 레코드와 레코드 집합의 필드 데이터 멤버 사이에서 데이터를 교환합니다.|  
|[CRecordset::Move](../Topic/CRecordset::Move.md)나 메뉴 또는 도구 모음 명령을 사용하여 레코드 집합을 스크롤합니다.|`DoFieldExchange`를 호출하여 현재의 새 레코드에서 필드 데이터 멤버로 데이터를 전송합니다.|  
|레코드를 추가, 업데이트 및 삭제합니다.|`DoFieldExchange`를 호출하여 데이터 소스로 데이터를 전송합니다.|  
  
## 참고 항목  
 [RFX](../../data/odbc/record-field-exchange-rfx.md)   
 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [레코드 집합: 합계 및 다른 집계 결과 구하기\(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [매크로, 전역 함수 및 전역 변수](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)