---
title: "레코드 필드 교환: RFX 함수 사용 | Microsoft Docs"
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
  - "데이터 형식[C++], ODBC 레코드 필드 교환"
  - "DoFieldExchange 메서드, RFX 함수"
  - "함수 호출, RFX 함수"
  - "ODBC[C++], 데이터 형식"
  - "ODBC[C++], RFX"
  - "RFX(ODBC)[C++], 데이터 형식"
  - "RFX(ODBC)[C++], 함수 구문 및 매개 변수"
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 필드 교환: RFX 함수 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 `DoFieldExchange` 재정의 본문을 구성하는 RFX 함수 호출의 사용 방법을 설명합니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 [CRecordset](../../mfc/reference/crecordset-class.md)에서 파생된 클래스에 적용됩니다.  대량 행 페치를 사용하는 경우 Bulk RFX\(대량 레코드 필드 교환\)가 구현됩니다.  Bulk RFX는 RFX와 비슷합니다.  차이점을 이해하려면 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 RFX 전역 함수는 데이터 소스의 열과 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환합니다.  RFX 함수 호출은 레코드 집합의 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 멤버 함수에 작성합니다.  이 항목에서는 해당 함수를 간단하게 설명하고 RFX 함수가 사용할 수 있는 데이터 형식을 보여 줍니다.  [Technical Note 43](../../mfc/tn043-rfx-routines.md)에서는 사용자가 추가 데이터 형식의 RFX 함수를 직접 작성하는 방법을 설명합니다.  
  
##  <a name="_core_rfx_function_syntax"></a> RFX 함수 구문  
 각 RFX 함수는 다음과 같은 세 개의 매개 변수를 사용합니다. 그러나 일부 RFX 함수는 선택적 요소인 네 번째나 다섯 번째의 매개 변수를 사용하는 경우도 있습니다.  
  
-   [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체에 대한 포인터.  `DoFieldExchange`로 전달되는 `pFX` 포인터와 함께 전달됩니다.  
  
-   데이터 소스에 표시되는 열 이름  
  
-   레코드 집합 클래스에 있는 해당 필드 데이터 멤버 또는 매개 변수 데이터 멤버의 이름  
  
-   \(선택 사항\) 일부 함수의 경우, 전송되는 문자열 또는 배열의 최대 길이.  기본값은 255바이트지만 사용자가 변경할 수 있습니다.  최대 크기는 `CString` 개체의 최대 크기인 **INT\_MAX**의 값\(2,147,483,647바이트\)을 기준으로 하지만 대개 이 크기보다는 드라이버 한계값에 제한을 받습니다.  
  
-   \(선택 사항\) `RFX_Text` 함수에서는 열의 데이터 형식을 지정하기 위해 다섯 번째 매개 변수를 사용하는 경우도 있습니다.  
  
 자세한 내용은 클래스 라이브러리 참조의 [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)에서 RFX 함수를 참조하십시오.  매개 변수를 특별하게 사용하는 경우에 대한 예제는 [레코드 집합: 합계 및 다른 집계 결과 구하기\(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)를 참조하십시오.  
  
##  <a name="_core_rfx_data_types"></a> RFX 데이터 형식  
 클래스 라이브러리는 데이터 소스와 레코드 집합 간에 서로 다른 다양한 데이터 형식을 전송하는 RFX 함수를 제공합니다.  다음 목록은 RFX 함수를 데이터 형식에 따라 요약한 것입니다.  사용자가 RFX 함수 호출을 직접 작성해야 하는 경우 데이터 형식에 따라 다음의 함수에서 선택하십시오.  
  
|Function|데이터 형식|  
|--------------|------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  
 자세한 내용은 클래스 라이브러리 참조의 [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)에서 RFX 함수 설명 부분을 참조하십시오.  C\+\+ 데이터 형식이 SQL 데이터 형식으로 매핑되는 방식에 대한 자세한 내용은 [SQL: SQL 및 C\+\+ 데이터 형식\(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)의 C\+\+ 데이터 형식에 매핑되는 ANSI SQL 데이터 형식 표를 참조하십시오.  
  
## 참고 항목  
 [RFX](../../data/odbc/record-field-exchange-rfx.md)   
 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)