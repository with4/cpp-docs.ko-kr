---
title: "레코드 집합: 대형 데이터 항목 작업(ODBC) | Microsoft Docs"
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
  - "이진 대형 개체"
  - "BLOB(이진 대형 개체), 레코드 집합"
  - "CLongBinary 클래스, 레코드 집합에서 사용"
  - "ODBC 레코드 집합, 이진 대형 개체"
  - "레코드 집합, 이진 대형 개체"
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 대형 데이터 항목 작업(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목의 내용은 MFC ODBC 클래스와 MFC DAO 클래스 모두에 적용됩니다.  
  
> [!NOTE]
>  MFC DAO 클래스를 사용하는 경우 [CLongBinary](../../mfc/reference/clongbinary-class.md) 클래스가 아니라 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스를 사용하여 대형 데이터 항목을 관리합니다.  대량 행 페치에 MFC ODBC 클래스를 사용하고 있으면 `CByteArray` 대신 `CLongBinary`를 사용하는 것이 좋습니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 여기에서는 사용자의 데이터베이스에서 비트맵\(직원 사진, 지도, 제품 그림, OLE 개체 등\)과 같은 대형 데이터를 저장할 수 있다고 가정합니다.  이런 종류의 데이터는 다음과 같은 특성이 있으므로 BLOB\(이진 대형 개체\)라고 합니다.  
  
-   각 필드 값이 큽니다.  
  
-   숫자나 다른 단순한 데이터 형식과 달리 크기를 예측할 수 없습니다.  
  
-   프로그램 상에서 데이터의 형식이 일정치 않습니다.  
  
 이 항목에서는 이러한 개체 작업을 위해 데이터베이스 클래스에서 제공하는 지원 기능에 대해 설명합니다.  
  
##  <a name="_core_managing_large_objects"></a> 대형 개체 관리  
 레코드 집합에는 이진 대형 개체를 쉽게 관리할 수 있는 두 가지 방법이 제공됩니다.  [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스나 [CLongBinary](../../mfc/reference/clongbinary-class.md) 클래스를 사용할 수 있습니다.  대개 `CByteArray`를 사용하여 대형 이진 개체를 관리합니다.  
  
 [CByteArray 클래스](#_core_the_cbytearray_class)에서 설명한 것처럼 `CByteArray`는 `CLongBinary`보다 오버헤드가 더 많이 발생하지만 성능은 더 좋습니다.  `CLongBinary`에 대한 간략한 설명은 [CLongBinary 클래스](#_core_the_clongbinary_class)를 참조하십시오.  
  
 `CByteArray`를 사용한 대형 데이터 항목 작업에 대한 자세한 내용은 [Technical Note 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) 문서를 참조하십시오.  
  
##  <a name="_core_the_cbytearray_class"></a> CByteArray 클래스  
 `CByteArray`는 MFC 컬렉션 클래스 중 하나입니다.  `CByteArray` 개체는 바이트의 동적 배열을 저장하며 배열은 필요에 따라 커질 수도 있습니다.  이 클래스는 기본 제공 C\+\+ 배열의 경우와 같이 인덱스를 사용하여 액세스 속도를 향상시킵니다.  진단을 목적으로 `CByteArray` 개체를 serialize하고 덤프할 수 있습니다.  이 클래스는 지정된 바이트를 가져오거나 설정하는 멤버 함수, 바이트를 삽입하거나 추가하는 멤버 함수 및 한 바이트나 모든 바이트를 제거하는 멤버 함수를 제공합니다.  이러한 기능을 이용하여 좀더 쉽게 이진 데이터를 구문 분석할 수 있습니다.  예를 들어 이진 개체가 OLE 개체인 경우 실제 개체에 도달하려면 일부 헤더 바이트를 통해 작업해야 합니다.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> 레코드 집합에서 CByteArray 사용  
 레코드 집합의 필드 데이터 멤버에 `CByteArray` 형식을 지정하면, [RFX](../../data/odbc/record-field-exchange-rfx.md)를 통해 레코드 집합과 데이터 소스 간의 개체 전송을 관리하고 개체 내의 데이터를 조작하는 데 유용하게 사용할 수 있습니다.  RFX는 검색된 데이터를 위한 고유 사이트가 필요하고 사용자는 내부 데이터에 액세스하기 위한 방법이 필요합니다.  
  
 `CByteArray`를 사용한 대형 데이터 항목 작업에 대한 자세한 내용은 [Technical Note 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) 문서를 참조하십시오.  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary 클래스  
 [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체는 힙에 할당된 저장소 블록에 대한 `HGLOBAL` 핸들과 관련되어 있는 간단한 셸입니다.  이 개체가 이진 대형 개체를 포함하는 테이블 열을 바인딩할 때 데이터를 레코드 집합에 전송해야 하면 RFX는 `HGLOBAL` 핸들을 할당하고 레코드 집합의 `CLongBinary` 필드에 핸들을 저장합니다.  
  
 그런 다음 다른 핸들 데이터와 마찬가지로 `HGLOBAL` 핸들의 `m_hData`를 사용하여 데이터 자체에 대한 작업을 수행합니다.  이 경우 [CByteArray](../../mfc/reference/cbytearray-class.md)가 유용합니다.  
  
> [!CAUTION]
>  CLongBinary 개체는 함수 호출 시 매개 변수로 사용할 수 없습니다.  뿐만 아니라 이 개체를 구현하면 **::SQLGetData**가 호출되므로 스크롤 가능한 스냅숏의 스크롤 속도가 느려집니다.  이 문제는 동적 스키마 열을 검색하기 위해 직접 **::SQLGetData** 호출을 사용하는 경우에도 발생할 수 있습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 합계 및 다른 집계 결과 구하기\(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [RFX](../../data/odbc/record-field-exchange-rfx.md)