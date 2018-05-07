---
title: 다이너셋 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec71b5b00b26564f9c8dc3c2d98f53f8182b0ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dynaset"></a>다이너셋
이 항목에서는 다이너셋 및 설명의 [가용성](#_core_availability_of_dynasets)합니다.  
  
> [!NOTE]
>  이 항목은 포함 하 여 MFC ODBC 클래스에 적용 됩니다. [CRecordset](../../mfc/reference/crecordset-class.md)합니다. 다이너셋 DAO 클래스에서에 대 한 정보를 참조 하십시오. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다. DAO를 사용 하 여 다이너셋 형식의 레코드 집합을 열 수 있습니다.  
  
 다이너셋 동적 속성을 가진 레코드 집합입니다. 다이너셋 모드 (일반적으로 다이너셋)의 레코드 집합 개체의 수명 동안 다음과 같은 방식으로 데이터 소스와 동기화가 유지 됩니다. 다중 사용자 환경에서 다른 사용자가 될 수 있습니다 편집 또는 다이너셋에 있는 레코드를 삭제 하거나 다이너셋 표시 하는 테이블에 레코드를 추가 합니다. 응용 프로그램에 추가 하거나 삭제 하는 레코드 집합에서 레코드 다이너셋에 반영 됩니다. 호출 하 여 다이너셋을 다시 만들 때까지 다른 사용자가 테이블에 추가 하는 레코드 다이너셋에 반영 되지 것입니다는 **Requery** 멤버 함수입니다. 다른 사용자가 레코드를 삭제, MFC 코드 레코드 집합의 삭제를 건너뜁니다. 다른 사용자의 기존 레코드를 편집 변경으로 스크롤할 때 영향을 받는 레코드 다이너셋에 반영 됩니다.  
  
 마찬가지로, 다이너셋의 레코드 편집 내용은 다이너셋을 사용할 다른 사용자가 반영 됩니다. 추가 된 레코드의 다이너셋 다시 쿼리 하기 전에 다른 사용자에 반영 되지 않습니다. 레코드를 삭제 하면 다른 사용자의 레코드 집합의 "삭제"된 것으로 표시 됩니다. 동일한 데이터베이스에 여러 연결이 있는 경우 (여러 `CDatabase` 개체), 그 연결과 관련 된 레코드 집합의 다른 사용자가 레코드 집합으로 동일한 상태를 포함 합니다.  
  
 다이너셋 가장 중요 한 때는 데이터 항공권 예약 시스템에서 (예:)으로 동적 이어야 합니다.  
  
> [!NOTE]
>  다이너셋을 사용 하려면 ODBC 드라이버는 다이너셋을 지 원하는 데이터 원본에 대 한 있고 ODBC 커서 라이브러리를 로드 하지 않아야 합니다. 자세한 내용은 참조 [다이너셋 가용성](#_core_availability_of_dynasets)합니다.  
  
 레코드 집합 다이너셋은 인지를 지정 하려면 전달 **CRecordset::dynaset** 에 첫 번째 매개 변수로 **열려** recordset 개체의 멤버 함수입니다.  
  
> [!NOTE]
>  업데이트할 수 있는 다이너셋에 대 한 ODBC 드라이버가 위치 지정된 update 문 중 하나를 지원 해야 합니다 또는 **:: SQLSetPos** ODBC API 함수입니다. MFC를 사용 하는 둘 다 지 원하는 경우 **:: SQLSetPos** 효율성에 대 한 합니다.  
  
##  <a name="_core_availability_of_dynasets"></a> 다이너셋 가용성  
 MFC 데이터베이스 클래스에는 다음 요구 사항을 충족 될 경우 다이너셋을 지원:  
  
-   ODBC 커서 라이브러리 DLL이 데이터 원본에 대 한 사용 아니어야 합니다.  
  
     커서 라이브러리를 사용 하는 경우 다이너셋 지원에 필요한 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 다이너셋을 사용 하려면 (및이 섹션의 나머지 부분에 설명 된 대로 ODBC 드라이버가 다이너셋에 필요한 기능을가지고) 하는 경우 MFC 만들 때 커서 라이브러리를 로드 하지 않도록 할 수 있습니다는 `CDatabase` 개체입니다. 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md) 및 [OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [열려](../../mfc/reference/cdatabase-class.md#open) 클래스의 멤버 함수 `CDatabase`합니다.  
  
     ODBC 용어로 다이너셋 및 스냅숏을 라고 커서입니다. 커서는 한 레코드 집합에서의 위치를 추적에 사용 되는 메커니즘입니다.  
  
-   데이터 원본에 대 한 ODBC 드라이버는 키 집합 커서를 지원 해야 합니다.  
  
     키 집합 커서를 가져오는 고 키 집합을 저장 하 여 테이블에서 데이터를 관리 합니다. 키가 현재 데이터를 가져오는 테이블에서 사용자가 특정 레코드를 스크롤할 때 사용 됩니다. 드라이버가이 지원 되는지 여부를 확인, 호출의 **:: SQLGetInfo** 와 ODBC API 함수는 **SQL_SCROLL_OPTIONS** 매개 변수입니다.  
  
     다이너셋의 키 집합을 지원 하지 않는 열려고 하는 경우 얻게는 `CDBException` 반환 코드 값을 가진 **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**합니다.  
  
-   데이터 원본에 대 한 ODBC 드라이버 확장 페치 지원 해야 합니다.  
  
     확장 페치는 뒤로 스크롤할 수 있을 뿐만 아니라 SQL 쿼리 결과 레코드에서 전달 하는 기능입니다. 을 드라이버에는이 기능을 지원 하는지 확인 하려면 호출는 **:: SQLGetFunctions** 와 ODBC API 함수는 **SQL_API_SQLEXTENDEDFETCH** 매개 변수입니다.  
  
 업데이트 가능한 다이너셋 (또는 해당 문제에 대 한 스냅숏을)을 하려는 경우 ODBC 드라이버가 지원 해야 하거나는 **:: SQLSetPos** ODBC API 함수 또는 위치 지정된 업데이트 합니다. **:: SQLSetPos** 함수에 SQL 문을 전송 하지 않고 데이터 소스를 업데이트 하는 MFC 할 수 있습니다. 이 지원을 사용할 수 있는 경우 MFC 한 SQL을 사용 하 여 업데이트를 수행 하는 대신 사용 됩니다. 드라이버 지원 하는지 확인 하려면 **:: SQLSetPos**, 호출 **:: SQLGetInfo** 와 **SQL_POS_OPERATIONS** 매개 변수입니다.  
  
 SQL 구문을 사용 하는 위치 지정된 업데이트 (폼의 **WHERE CURRENT OF** \<m e >)를 데이터 원본에 있는 테이블에서 특정 행을 식별 합니다. 을 드라이버에 위치 지정된 업데이트를 지원 하는지 확인 하려면 호출 **:: SQLGetInfo** 와 **SQL_POSITIONED_STATEMENTS** 매개 변수입니다.  
  
 일반적으로 MFC 다이너셋 (그러나 정방향 전용 레코드 집합)에 수준 2 API 규칙을 한 ODBC 드라이버가 필요 합니다. 데이터 원본에 대 한 드라이버 수준 1 API 집합을 따르는 경우 모두 업데이트 가능 하 고 읽기 전용 스냅숏을 앞 으로만 이동 가능한 레코드 집합 있지만 하지 다이너셋 여전히 사용할 수 있습니다. 그러나 수준 1 드라이버는 다이너셋을 확장 패치 하는 경우 및 키 집합 커서를 지원할 수 있습니다. ODBC 받는 규칙 수준에 대 한 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md)합니다.  
  
> [!NOTE]
>  스냅숏과 다이너셋 사용 하려는 경우 두 개의 다른에 기반 해야 `CDatabase` 개체 (두 개의 서로 다른 연결).  
  
 ODBC 커서 라이브러리에서 관리 하는 중간 저장소를 사용 하는 스냅숏, 달리 다이너셋 스크롤 하는 즉시 데이터 원본에서 직접 레코드를 인출 합니다. 이렇게 하면 원래 데이터 원본과 동기화 다이너셋에서 선택한 레코드.  
  
 이 버전의 Visual c + +에 포함 된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대 한 정보에 대 한 참조 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)