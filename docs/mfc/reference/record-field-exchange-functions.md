---
title: "레코드 필드 교환 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO(Data Access Objects), 레코드 필드 교환(DFX)"
  - "ODBC, 대량 RFX 데이터 교환 함수"
  - "RFX(레코드 필드 교환), ODBC 클래스"
  - "DFX(DAO 레코드 필드 교환), 데이터 교환 함수"
  - "DFX 함수"
  - "대량 RFX 함수"
  - "DFX(DAO 레코드 필드 교환)"
  - "RFX(레코드 필드 교환), DAO 클래스"
  - "ODBC, RFX"
  - "RFX(레코드 필드 교환), 데이터 교환 함수"
  - "RFX(레코드 필드 교환)"
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 필드 교환 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 레코드 집합 개체와 해당 데이터 소스 간의 데이터 전송을 자동화하고 데이터에 대한 다른 작업을 수행하는 데 사용되는 레코드 필드 교환\([RFX](#_mfc_rfx_functions_.28.odbc.29), [대량 RFX](#_mfc_bulk_rfx_functions_.28.odbc.29), 및 [DFX](#_mfc_dfx_functions_.28.dao.29)\) 함수를 나열합니다.  
  
 ODBC 기반 클래스를 사용하고 대량 행 페치를 구현한 경우 데이터 소스 열에 해당하는 각 데이터 멤버에 대해 대량 RFX 함수를 호출하여 `CRecordset`의 `DoBulkFieldExchange` 멤버 함수를 수동으로 재정의해야 합니다.  
  
 ODBC 기반 클래스에서 대량 행 페치를 구현하지 않았거나 DAO 기반 클래스를 사용하는 경우에는 클래스 마법사가 레코드 집합의 각 필드 데이터 멤버에 대해 RFX 함수\(ODBC 클래스의 경우\) 또는 DFX 함수\(DAO 클래스의 경우\)를 호출하여 `CRecordset` 또는 `CDaoRecordset`의 `DoFieldExchange` 멤버 함수를 재정의합니다.  
  
 레코드 필드 교환 함수는 프레임워크에서 `DoFieldExchange` 또는 `DoBulkFieldExchange`를 호출할 때마다 데이터를 전송합니다. 각 함수는 특정 데이터 형식을 전송합니다.  
  
 이러한 함수의 사용 방법에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식\(ODBC\)](../../data/odbc/record-field-exchange-how-rfx-works.md) 문서를 참조하세요. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 문서를 참조하세요.  
  
 동적으로 바인딩하는 데이터 열의 경우 [레코드 집합: 데이터 열 동적 바인딩 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) 문서에 설명된 대로 RFX 또는 DFX 함수를 직접 호출할 수도 있습니다. 또한 Technical Note [43](../../mfc/tn043-rfx-routines.md)\(ODBC\) 및 Technical Note [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)\(DAO\)에 설명된 대로 사용자 고유의 사용자 지정 RFX 또는 DFX 루틴을 작성할 수 있습니다.  
  
 `DoFieldExchange` 및 `DoBulkFieldExchange` 함수에 표시되는 RFX 및 대량 RFX 함수에 대한 예제는 [RFX\_Text](../Topic/RFX_Text.md) 및 [RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)를 참조하세요. DFX 함수는 RFX 함수와 매우 유사합니다.  
  
### RFX 함수\(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary](../Topic/RFX_Binary.md)|[CByteArray](../../mfc/reference/cbytearray-class.md) 형식의 바이트 배열을 전송합니다.|  
|[RFX\_Bool](../Topic/RFX_Bool.md)|부울 데이터를 전송합니다.|  
|[RFX\_Byte](../Topic/RFX_Byte.md)|단일 바이트 데이터를 전송합니다.|  
|[RFX\_Date](../Topic/RFX_Date.md)|[CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 **TIMESTAMP\_STRUCT**를 사용하여 시간 및 날짜 데이터를 전송합니다.|  
|[RFX\_Double](../Topic/RFX_Double.md)|배정밀도 부동 소수점 수 데이터를 전송합니다.|  
|[RFX\_Int](../Topic/RFX_Int.md)|정수 데이터를 전송합니다.|  
|[RFX\_Long](../Topic/RFX_Long.md)|정수\(Long\) 데이터를 전송합니다.|  
|[RFX\_LongBinary](../Topic/RFX_LongBinary.md)|[CLongBinary](../../mfc/reference/clongbinary-class.md) 클래스의 개체와 함께 BLOB\(Binary Large Object\) 데이터를 전송합니다.|  
|[RFX\_Single](../Topic/RFX_Single.md)|부동 소수점 수 데이터를 전송합니다.|  
|[RFX\_Text](../Topic/RFX_Text.md)|문자열 데이터를 전송합니다.|  
  
### 대량 RFX 함수\(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary\_Bulk](../Topic/RFX_Binary_Bulk.md)|바이트 데이터 배열을 전송합니다.|  
|[RFX\_Bool\_Bulk](../Topic/RFX_Bool_Bulk.md)|부울 데이터 배열을 전송합니다.|  
|[RFX\_Byte\_Bulk](../Topic/RFX_Byte_Bulk.md)|단일 바이트 배열을 전송합니다.|  
|[RFX\_Date\_Bulk](../Topic/RFX_Date_Bulk.md)|**TIMESTAMP\_STRUCT** 형식의 데이터 배열을 전송합니다.|  
|[RFX\_Double\_Bulk](../Topic/RFX_Double_Bulk.md)|배정밀도 부동 소수점 데이터 배열을 전송합니다.|  
|[RFX\_Int\_Bulk](../Topic/RFX_Int_Bulk.md)|정수 데이터 배열을 전송합니다.|  
|[RFX\_Long\_Bulk](../Topic/RFX_Long_Bulk.md)|정수\(Long\) 데이터 배열을 전송합니다.|  
|[RFX\_Single\_Bulk](../Topic/RFX_Single_Bulk.md)|부동 소수점 데이터 배열을 전송합니다.|  
|[RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)|**LPSTR** 형식의 데이터 배열을 전송합니다.|  
  
### DFX 함수\(DAO\)  
  
|||  
|-|-|  
|[DFX\_Binary](../Topic/DFX_Binary.md)|[CByteArray](../../mfc/reference/cbytearray-class.md) 형식의 바이트 배열을 전송합니다.|  
|[DFX\_Bool](../Topic/DFX_Bool.md)|부울 데이터를 전송합니다.|  
|[DFX\_Byte](../Topic/DFX_Byte.md)|단일 바이트 데이터를 전송합니다.|  
|[DFX\_Currency](../Topic/DFX_Currency.md)|[COleCurrency](../../mfc/reference/colecurrency-class.md) 형식의 통화 데이터를 전송합니다.|  
|[DFX\_DateTime](../Topic/DFX_DateTime.md)|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 형식의 날짜 및 시간 데이터를 전송합니다.|  
|[DFX\_Double](../Topic/DFX_Double.md)|배정밀도 부동 소수점 수 데이터를 전송합니다.|  
|[DFX\_Long](../Topic/DFX_Long.md)|정수\(Long\) 데이터를 전송합니다.|  
|[DFX\_LongBinary](../Topic/DFX_LongBinary.md)|`CLongBinary` 클래스의 개체와 함께 BLOB\(Binary Large Object\) 데이터를 전송합니다. DAO의 경우 대신 [DFX\_Binary](../Topic/DFX_Binary.md)를 사용하는 것이 좋습니다.|  
|[DFX\_Short](../Topic/DFX_Short.md)|정수\(Short\) 데이터를 전송합니다.|  
|[DFX\_Single](../Topic/DFX_Single.md)|부동 소수점 수 데이터를 전송합니다.|  
|[DFX\_Text](../Topic/DFX_Text.md)|문자열 데이터를 전송합니다.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)   
 [CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)   
 [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)