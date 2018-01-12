---
title: "ODBC: ODBC 커서 라이브러리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d849580ce3e9b264c854633c6bb9f274874c21d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC 커서 라이브러리
이 항목에서 ODBC 커서 라이브러리 및 사용 하는 방법을 설명 합니다. 자세한 내용은 다음을 참조하세요.  
  
-   [커서 라이브러리와 수준 1 ODBC 드라이버](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [위치 지정된 업데이트 및 타임 스탬프 열](#_core_positioned_updates_and_timestamp_columns)  
  
-   [커서 라이브러리 사용](#_core_using_the_cursor_library)  
  
 ODBC 커서 라이브러리는 ODBC 드라이버 관리자와 드라이버 사이 있는 동적 연결 라이브러리 (DLL). ODBC에서, 드라이버를 레코드 집합에서의 위치를 추적 하는 커서를 유지 관리 합니다. 커서가 이미 스크롤 했는지 레코드 집합의 위치를 표시 합니다.-현재 레코드입니다.  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a>커서 라이브러리와 수준 1 ODBC 드라이버  
 ODBC 커서 라이브러리는 다음과 같은 새로운 기능 수준 1 드라이버를 제공 합니다.  
  
-   앞 이나 뒤로 스크롤입니다. 수준 2 드라이버 커서 라이브러리를 스크롤할 수 있는 이미 있기 때문에 필요 하지 않습니다.  
  
-   스냅숏 지원 합니다. 커서 라이브러리는 스냅숏의 레코드를 포함 하는 버퍼를 관리 합니다. 이 버퍼는 프로그램의 삭제 및 편집 레코드 있지만 하지는 추가, 삭제, 또는 다른 사용자의 편집 작업을 반영합니다. 따라서 스냅숏은 현재 커서 라이브러리 버퍼만 있습니다. 버퍼 또한 반영 하지 않습니다 사용자 고유의 추가 호출할 때까지 **Requery**합니다. 다이너셋 커서 라이브러리를 사용 하지 마십시오.  
  
 커서 라이브러리는 드라이버에서 지원 하지 않는 경우에 스냅숏 (정적 커서)를 제공 합니다. 드라이버가 정적 커서를 이미 지원 스냅숏 지원을 받는 커서 라이브러리를 로드할 필요가 없습니다. 커서 라이브러리를 사용 하는 경우에 스냅숏 및 앞 으로만 이동 가능한 레코드 집합을 사용할 수 있습니다. 드라이버 지원 다이너셋 (KEYSET_DRIVEN 커서) 사용 하려면 하는 경우에 커서 라이브러리를 사용 해야 합니다. 스냅숏과 다이너셋 사용 하려는 경우 두 개의 다른에 기반 해야 `CDatabase` 드라이버가 둘 다 지원 하지 않는 한 (두 개의 서로 다른 연결) 개체입니다.  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a>위치 지정된 업데이트 및 타임 스탬프 열  
  
> [!NOTE]
>  ODBC 데이터 소스는이 항목에 설명 된 대로 MFC ODBC 클래스를 통해 또는 MFC 데이터 액세스 개체 (DAO) 클래스를 통해 액세스할 수 있습니다.  
  
> [!NOTE]
>  ODBC 드라이버가 지원 **SQLSetPos**, 어떤 MFC 사용 가능한 경우,이 항목에 적용 되지 않습니다.  
  
 대부분의 수준 1 드라이버 위치 지정된 업데이트를 지원 하지 않습니다. 이러한 드라이버는 이런 점에서 수준 2 드라이버의 기능을 에뮬레이트하는 데 커서 라이브러리에 의존 합니다. 커서 라이브러리는 변경 되지 않은 필드에 대 한 검색 결과 업데이트를 수행 하 여 위치 지정된 업데이트 지원을 에뮬레이션 합니다.  
  
 경우에 따라 레코드 집합 변경 되지 않은 이러한 필드 중 하나로 타임 스탬프 열을 포함 될 수 있습니다. MFC 레코드 집합을 사용 하 여 타임 스탬프 열이 포함 된 테이블에서 두 가지 문제가 발생 합니다.  
  
 첫 번째 문제는 타임 스탬프 열이 있는 테이블에 대 한 스냅숏을 업데이트할 수와 관련 됩니다. 스냅숏의 바인딩되는 테이블에 타임 스탬프 열이 포함 된 경우 호출 해야 **Requery** 호출한 후 **편집** 및 **업데이트**합니다. 그렇지 않으면 동일한 레코드를 다시 편집 못할 수 있습니다. 호출 하는 경우 **편집** 차례로 **업데이트**, 데이터 원본에는 레코드가 기록 되기 및 타임 스탬프 열이 업데이트 됩니다. 호출 하지 않으면 **Requery**, 스냅숏의 레코드에 대 한 타임 스탬프 값은 데이터 원본에 대해 해당 타임 스탬프를 더 이상 일치 합니다. 레코드를 다시 업데이트 하려고 할 때 데이터 소스는 불일치 때문에 업데이트를 허용 하지 수 있습니다.  
  
 클래스의 제한 사항과 관련 된 두 번째 문제 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 와 함께 사용할 경우의 `RFX_Date` 함수를 테이블로 또는 테이블에서 날짜 및 시간 정보를 전송 합니다. 처리는 `CTime` 개체 형식으로 데이터 전송 동안 중간 처리 오버 헤드가 있습니다. 날짜 범위 `CTime` 개체 수 또한 너무 제한적일 수 일부 응용 프로그램에 대 한 합니다. 새 버전의는 `RFX_Date` 함수는 ODBC 사용 **TIMESTAMP_STRUCT** 매개 변수 대신는 `CTime` 개체입니다. 자세한 내용은 참조 `RFX_Date` 에 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *MFC 참조*합니다.  

  
##  <a name="_core_using_the_cursor_library"></a>커서 라이브러리 사용  
 데이터 원본에 연결할 때-호출 하 여 [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) -커서 라이브러리를 사용 하 여 데이터 원본에 대 한 것인지를 지정할 수 있습니다. 해당 데이터 원본에 스냅숏 만들기는, 지정는 **CDatabase::useCursorLib** 옵션에 `dwOptions` 매개 변수를 `OpenEx` 지정 또는 **TRUE** 에 대 한는  **bUseCursorLib** 매개 변수를 **열려** (기본값은 **TRUE**). ODBC 드라이버가 지 원하는 경우 데이터 원본에서 다이너셋을 열려는 (것 다이너셋을 일부 드라이버 기능을 마스크) 커서 라이브러리를 사용 하지 마십시오. 이 경우 지정 하지 않으면 **CDatabase::useCursorLib** 에 `OpenEx` 지정 또는 **FALSE** 에 대 한는 **bUseCursorLib** 매개 변수에서 **열**.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 기본 사항](../../data/odbc/odbc-basics.md)