---
title: "ODBC: ODBC 커서 라이브러리 | Microsoft Docs"
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
  - "커서 라이브러리[ODBC]"
  - "커서 라이브러리[ODBC], 스냅샷"
  - "커서, ODBC 커서 라이브러리"
  - "수준 1 ODBC 드라이버"
  - "ODBC 커서 라이브러리[ODBC]"
  - "ODBC 드라이버, 커서 지원"
  - "ODBC 드라이버, 수준 1"
  - "ODBC, 타임스탬프"
  - "위치 지정 업데이트"
  - "커서 위치 조정"
  - "스냅샷, ODBC 지원"
  - "정적 커서"
  - "타임스탬프, ODBC 타임스탬프 열"
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ODBC: ODBC 커서 라이브러리
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 ODBC 커서 라이브러리 및 사용법에에 대해 설명합니다.  자세한 내용은 다음을 참조하십시오.  
  
-   [커서 라이브러리와 수준 1 ODBC 드라이버](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [위치 지정 업데이트와 타임스탬프 열](#_core_positioned_updates_and_timestamp_columns)  
  
-   [커서 라이브러리 사용](#_core_using_the_cursor_library)  
  
 ODBC 커서 라이브러리는 ODBC 드라이버 관리자와 드라이버 사이에 위치하는 동적 연결 라이브러리입니다.  ODBC 용어로 드라이버는 커서를 관리하여 레코드 집합에서 위치를 추적합니다.  커서는 레코드 집합에서 이미 스크롤한 위치, 즉 현재 레코드를 표시합니다.  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> 커서 라이브러리와 수준 1 ODBC 드라이버  
 ODBC 커서 라이브러리는 수준 1 드라이버에 다음과 같은 새 기능을 제공합니다.  
  
-   앞과 뒤로 스크롤할 수 있는 기능.  수준 2 드라이버는 스크롤이 가능하므로 커서 라이브러리가 필요없습니다.  
  
-   스냅숏 지원.  커서 라이브러리는 스냅숏의 레코드를 포함하는 버퍼를 관리합니다.  이 버퍼는 레코드에 대한 프로그램의 삭제 및 편집을 반영하지만 다른 사용자의 추가, 삭제 또는 편집은 반영하지 않습니다.  따라서 스냅숏은 커서 라이브러리의 버퍼 상태를 기준으로 합니다.  또한 버퍼는 **Requery**를 호출하기 전에는 사용자가 수행한 레코드 추가를 반영하지 않습니다.  다이너셋은 커서 라이브러리를 사용하지 않습니다.  
  
 커서 라이브러리는 드라이버에서 지원하지 않는 경우에도 스냅숏\(정적 커서\)을 제공합니다.  드라이버가 이미 정적 커서를 지원하면 스냅숏 지원을 위해 커서 라이브러리를 로드할 필요가 없습니다.  커서 라이브러리를 사용할 때는 스냅숏이나 앞으로만 이동 가능한 레코드 집합만을 사용할 수 있습니다.  드라이버가 다이너셋\(KEYSET\_DRIVEN 커서\)을 지원하는 경우 이를 사용하려면 커서 라이브러리를 사용할 수 없습니다.  스냅숏과 다이너셋 모두를 사용하려는 경우 드라이버가 이들 모두를 지원하지 않으면 서로 다른 두 개의 `CDatabase` 개체\(서로 다른 두 개의 연결\)에 기반해야 합니다.  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a> 위치 지정 업데이트와 타임스탬프 열  
  
> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC DAO\(데이터 액세스 개체\) 클래스를 통해서도 액세스할 수 있습니다.  
  
> [!NOTE]
>  ODBC 드라이버가 **SQLSetPos**를 지원하는 경우에는 MFC에서 이를 사용하므로 이 항목은 적용되지 않습니다.  
  
 대부분의 수준 1 드라이버는 위치 지정 업데이트를 지원하지 않습니다.  이러한 드라이버는 커서 라이브러리를 통해 수준 2 드라이버의 기능을 에뮬레이션합니다.  커서 라이브러리는 변경되지 않은 필드에서 검색 업데이트를 수행하여 위치 지정 업데이트 지원을 에뮬레이션합니다.  
  
 경우에 따라 레코드 집합은 변경되지 않은 필드의 하나로 타임스탬프 열을 포함할 수도 있습니다.  타임스탬프 열을 포함하는 테이블을 MFC 레코드 집합과 함께 사용하는 경우 두 가지 문제가 발생합니다.  
  
 첫째는 타임스탬프 열을 포함하는 테이블의 업데이트 가능한 스냅숏과 관련된 문제입니다.  스냅숏이 바인딩된 테이블에 타임스탬프 열이 있으면 **Edit**와 **Update**를 호출한 후 **Requery**를 호출해야 합니다.  그렇지 않으면 해당 레코드를 다시 편집하지 못할 수도 있습니다.  **Edit**를 호출한 다음 **Update**를 호출하면 데이터 소스에 레코드가 기록되고 타임스탬프 열이 업데이트되지만  **Requery**를 호출하지 않으면 스냅숏의 레코드에 대한 타임스탬프 값은 더 이상 데이터 소스의 해당 타임스탬프와 일치하지 않게 됩니다.  따라서 레코드를 다시 업데이트하려고 하면 이로 인해 데이터 소스에서 업데이트를 허용하지 않을 수도 있습니다.  
  
 둘째는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 클래스를 `RFX_Date` 함수와 함께 사용하여 테이블에서 또는 테이블로 시간 및 날짜 정보를 전송할 때 발생하는 제한 사항과 관련된 문제입니다.  `CTime` 개체를 처리하려면 데이터를 전송하는 동안 중간 처리 과정이 추가되므로 오버헤드가 발생합니다.  `CTime` 개체의 날짜 범위는 일부 응용 프로그램에서는 충분하지 않을 수도 있습니다.  따라서 새 버전의`RFX_Date`함수에서는 `CTime` 개체 대신 ODBC **TIMESTAMP\_STRUCT** 매개 변수를 사용합니다.  자세한 내용은 MFC 참조의 [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)에서 `RFX_Date` 함수를 참조하십시오.  
  
##  <a name="_core_using_the_cursor_library"></a> 커서 라이브러리 사용  
 [CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md) 또는 [CDatabase::Open](../Topic/CDatabase::Open.md)을 호출하여 데이터 소스에 연결할 때 데이터 소스에 커서 라이브러리를 사용할지 여부를 지정할 수 있습니다.  해당 데이터 소스에서 스냅숏을 만드는 경우 `OpenEx`의 `dwOptions` 매개 변수에 **CDatabase::useCursorLib** 옵션을 지정하거나 **Open**의 **bUseCursorLib** 매개 변수에 **TRUE**를 지정해야 합니다. 기본값은 **TRUE**입니다.  ODBC 드라이버가 다이너셋을 지원하는 경우 데이터 소스에서 다이너셋을 열려면 커서 라이브러리를 사용하지 않는 것이 좋습니다. 이 경우 커서 라이브러리를 사용하면 다이너셋에 필요한 일부 드라이버의 기능이 제한될 수 있습니다.  따라서 `OpenEx`에 **CDatabase::useCursorLib** 옵션을 지정하거나 **Open**의 **bUseCursorLib** 매개 변수에 **FALSE** 값을 지정하지 않는 것이 좋습니다.  
  
## 참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)