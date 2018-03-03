---
title: "레코드 집합: 대형 데이터 항목 (ODBC) 작업 | Microsoft Docs"
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
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf82e1fabd45e9bccd63e4ba46068b75d2c2a0a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-working-with-large-data-items-odbc"></a>레코드 집합: 대형 데이터 항목 작업(ODBC)
이 항목 MFC ODBC 클래스와 MFC DAO 클래스에 적용 됩니다.  
  
> [!NOTE]
>  MFC DAO 클래스를 사용 하는 경우 클래스가 있는 대형 데이터 항목을 관리 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스 대신 [CLongBinary](../../mfc/reference/clongbinary-class.md)합니다. 대량 행 페치와 MFC ODBC 클래스를 사용 하는 경우 사용 하 여 `CLongBinary` 대신 `CByteArray`합니다. 대량 행 페치에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 사용자의 데이터베이스 대형 비트맵 (직원 사진을, 지도, 제품 그림, OLE 개체)과 같은 데이터를 저장할 수 있다고 가정 합니다. 이러한 종류의 데이터는 라고도 Binary Large Object (또는 BLOB) 때문에:  
  
-   각 필드 값이 큽니다.  
  
-   숫자 및 다른 단순한 데이터 형식과 달리 크기를 예측할 수 없습니다.  
  
-   데이터는 프로그램의 일정치 합니다.  
  
 이 항목에서는 이러한 개체로 작업 하기 위한 데이터베이스 클래스에서 제공 하는 지원 기능에 대해 설명 합니다.  
  
##  <a name="_core_managing_large_objects"></a>대형 개체 관리  
 레코드 집합에는 이진 대형 개체 관리를 쉽게 해결 하기 위해 다음의 두 가지입니다. 클래스를 사용할 수 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스를 사용할 수 있습니다 또는 [CLongBinary](../../mfc/reference/clongbinary-class.md)합니다. 일반적으로 `CByteArray` 은 큰 이진 데이터를 관리 하는 것이 좋습니다.  
  
 `CByteArray`보다 더 많은 오버 헤드가 필요 `CLongBinary` 성능은 더에 설명 된 대로 하지만 [CByteArray 클래스](#_core_the_cbytearray_class)합니다. `CLongBinary`간단히 설명 [CLongBinary 클래스](#_core_the_clongbinary_class)합니다.  
  
 사용에 대 한 자세한 내용은 `CByteArray` 대형 데이터 항목을 사용 하려면 참조 [기술 참고 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)합니다.  
  
##  <a name="_core_the_cbytearray_class"></a>CByteArray 클래스  
 `CByteArray`MFC 컬렉션 클래스 중 하나입니다. A `CByteArray` 개체 바이트의 동적 배열을 저장-필요에 따라 배열 커질 수 있습니다. 클래스는 기본 제공 c + + 배열와 마찬가지로 인덱스로 빠른 액세스를 제공 합니다. `CByteArray`개체를 serialize 및 진단용으로 덤프할 수 있습니다. 가져오기 및 지정 된 바이트를 설정, 삽입 및 바이트를 추가 및 1 바이트 또는 바이트를 모두 제거 하기 위한 멤버 함수를 제공 하는 클래스입니다. 이러한 시설은 이진 데이터를 보다 쉽게 구문 분석을 확인 합니다. 예를 들어 이진 개체가 OLE 개체 이면에 실제 개체에 도달 하기 위해 일부 헤더 바이트를 진행 해야 합니다.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a>CByteArray 레코드 집합에서 사용  
 레코드 집합의 필드 데이터 멤버 유형을 지정 하 여 `CByteArray`, 고정된 한 자료를 제공 [RFX](../../data/odbc/record-field-exchange-rfx.md) 조작할 수 있습니다 및 레코드 집합 및 데이터 원본 간에 이러한 개체 전송을 관리는 개체 내의 데이터입니다. RFX에 대 한 검색 된 데이터를 특정 사이트를 필요 하 고 기본 데이터에 액세스 하는 방법이 필요 합니다.  
  
 사용에 대 한 자세한 내용은 `CByteArray` 대형 데이터 항목을 사용 하려면 참조 [기술 참고 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)합니다.  
  
##  <a name="_core_the_clongbinary_class"></a>CLongBinary 클래스  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체는 주위 간단한 셸은 `HGLOBAL` 힙에 할당 된 저장소의 블록에 대 한 핸들입니다. 이진 대형 개체를 포함 하는 테이블 열을 바인딩할 때 RFX 할당는 `HGLOBAL` 레코드 집합에 데이터를 전송 해야 하 고에 핸들을 저장 하는 경우 처리는 `CLongBinary` 레코드 집합의 필드입니다.  
  
 를 사용 하 여는 `HGLOBAL` 처리, `m_hData`,으로 처리할 수 있습니다에 데이터에 연산을 자체 데이터로 작업 하 합니다. 여기에 [CByteArray](../../mfc/reference/cbytearray-class.md) 기능을 추가 합니다.  
  
> [!CAUTION]
>  CLongBinary 개체 함수 호출에 매개 변수로 사용할 수 없습니다. 또한를 호출 하는 구현 **:: SQLGetData**, 반드시 스크롤 스크롤 가능한 스냅숏의 속도가 느려집니다. 이 경우도 마찬가지 사용 하는 경우는 **:: SQLGetData** 동적 스키마 열을 검색 하기 위해 직접 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 합계 및 다른 집계 결과 (ODBC) 구하기](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)