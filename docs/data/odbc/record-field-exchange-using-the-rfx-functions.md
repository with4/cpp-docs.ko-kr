---
title: "레코드 필드 교환: RFX 함수 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a270b26fc0fd9be721ee0656f9f0d14ab579b477
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>레코드 필드 교환: RFX 함수 사용
이 항목의 본문을 구성 하는 RFX 함수 호출을 사용 하는 방법에 설명 프로그램 `DoFieldExchange` 재정의 합니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다. [CRecordset](../../mfc/reference/crecordset-class.md) 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 RFX 전역 함수에 표시 되는 데이터 원본 및 필드 데이터 멤버 레코드 집합의 열 간에 데이터를 교환 합니다. RFX 함수 호출에서 레코드 집합의 쓰기 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 멤버 함수입니다. 이 항목에서는 해당 함수를 간단 하 게 하 고 함수를 사용할 수 있는 RFX에 대 한 데이터 형식을 보여 줍니다. [기술 참고 43](../../mfc/tn043-rfx-routines.md) 추가 데이터 형식에 대해 RFX 함수를 직접 작성 하는 방법에 설명 합니다.  
  
##  <a name="_core_rfx_function_syntax"></a>RFX 함수 구문  
 세 개의 매개 변수를 사용 하는 각 RFX 함수 (및 선택적 4 또는 5 번째 매개 변수 사용):  
  
-   에 대 한 포인터는 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체입니다. 함께 전달 됩니다는 `pFX` 포인터에 전달 `DoFieldExchange`합니다.  
  
-   데이터 원본에는 열의 이름을 표시 됩니다.  
  
-   해당 필드 데이터 멤버 또는 레코드 집합 클래스의 매개 변수 데이터 멤버의 이름입니다.  
  
-   (선택 사항) 일부는 함수, 전송 되는 배열 또는 문자열의 최대 길이입니다. 기본값은 255 바이트 있지만 변경 수 있습니다. 최대 크기의 최대 크기에 따라는 `CString` 개체- **INT_MAX** (2147483647) 바이트인-크기에 드라이버 한계값 아마도 하지만 합니다.  
  
-   (선택 사항) 에 `RFX_Text` 함수를 경우가 다섯 번째 매개 변수를 통해 데이터 형식의 열을 지정 합니다.  
  
 자세한 내용은 아래 RFX 함수를 참조 하십시오. [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *클래스 라이브러리 참조*합니다. 특별 한 수행할 수 있는 경우의 예에 대 한 매개 변수를 참조 하십시오 [레코드 집합: 합계 및 구하기 다른 집계 결과 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)합니다.  
  
##  <a name="_core_rfx_data_types"></a>RFX 데이터 형식  
 클래스 라이브러리는 여러 다른 데이터 형식을 데이터 소스와 레코드 집합 간 전송에 대해 RFX 함수를 제공 합니다. 데이터 형식별 RFX 함수를 다음과 같습니다. RFX 함수 호출에 직접 작성 해야 하는 경우에서 데이터 형식에서 이러한 함수에서 선택 합니다.  
  
|함수|데이터 형식|  
|--------------|---------------|  
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
  

 자세한 내용은 아래 RFX 함수 설명서를 참조 하십시오. [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *클래스 라이브러리 참조*합니다. C + + 데이터 형식이 SQL 데이터 형식으로 매핑되는 방법에 대 한 내용은 c + + 데이터 형식에 매핑되는 ANSI SQL 데이터 형식 표를 참조에서 [SQL: SQL 및 c + + 데이터 형식 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 필드 교환 (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [레코드 집합: 데이터 열 (ODBC)을 동적으로 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)