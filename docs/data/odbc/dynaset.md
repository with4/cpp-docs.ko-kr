---
title: "다이너셋 | Microsoft Docs"
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
  - "커서 라이브러리[ODBC], 다이너셋 가용성"
  - "커서[ODBC], 다이너셋의 키 집합 구동 커서"
  - "다이너셋"
  - "다이너셋의 키 집합 구동 커서"
  - "ODBC 커서 라이브러리[ODBC], 다이너셋"
  - "ODBC 레코드 집합, 다이너셋"
  - "레코드 집합[C++], 다이너셋"
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다이너셋
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 다이너셋 및 다이너셋의 [가용성](#_core_availability_of_dynasets)에 대해 설명합니다.  
  
> [!NOTE]
>  이 항목의 내용은 [CRecordset](../../mfc/reference/crecordset-class.md)을 포함하여 MFC ODBC 클래스에 적용됩니다.  DAO 클래스의 다이너셋에 대한 내용은 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)을 참조하십시오.  DAO를 사용하여 다이너셋 형식의 레코드 집합을 열 수 있습니다.  
  
 다이너셋은 동적 속성을 가진 레코드 집합입니다.  다이너셋 모드의 레코드 집합 개체\(일반적으로 다이너셋\)는 수명이 지속되는 동안 다음과 같은 방법으로 데이터 소스와 동기화가 유지됩니다.  다중 사용자 환경에서는 다른 사용자가 다이너셋의 레코드를 편집, 삭제하거나 다이너셋이 표시하는 테이블에 레코드를 추가할 수 있습니다.  응용 프로그램이 레코드 집합에 추가하거나 레코드 집합에서 삭제하는 레코드는 다이너셋에 반영됩니다.  다른 사용자가 테이블에 추가하는 레코드는 **Requery** 멤버 함수를 호출하여 다이너셋을 다시 만들 때까지 반영되지 않습니다.  다른 사용자가 레코드를 삭제할 때 MFC 코드는 레코드 집합에서 삭제된 레코드를 건너뜁니다.  다른 사용자가 기존 레코드를 편집하여 변경한 내용은 영향을 받은 레코드로 스크롤할 때 즉시 다이너셋에 반영됩니다.  
  
 마찬가지로 다이너셋의 레코드를 편집하면 다른 사용자가 다이너셋을 사용할 때 반영됩니다.  추가된 레코드는 다른 사용자가 다이너셋을 다시 쿼리하기 전에는 다른 사용자의 다이너셋에 반영되지 않습니다.  삭제된 레코드는 다른 사용자의 레코드 집합에 삭제된 것으로 표시됩니다.  동일한 데이터베이스에 대해 다중 연결을 사용하는 경우\(다중 `CDatabase` 개체\) 그 연결과 관련된 레코드 집합은 다른 사용자의 레코드 집합과 동일한 상태를 유지합니다.  
  
 다이너셋은 항공권 예약 시스템 같이 동적인 데이터를 사용할 때 가장 유용합니다.  
  
> [!NOTE]
>  다이너셋을 사용하려면 해당 데이터 소스에 대해 다이너셋을 지원하는 ODBC 드라이버가 필요하며 ODBC 커서 라이브러리를 로드하지 않아야 합니다.  자세한 내용은 [다이너셋 가용성](#_core_availability_of_dynasets)을 참조하십시오.  
  
 레코드 집합을 다이너셋으로 지정하려면 레코드 집합 개체의 **Open** 멤버 함수의 첫째 매개 변수로 **CRecordset::dynaset**을 전달합니다.  
  
> [!NOTE]
>  업데이트 가능한 다이너셋을 사용하려면 ODBC 드라이버가 위치 지정 업데이트 문이나 **::SQLSetPos** ODBC API 함수를 지원해야 합니다.  둘 다 지원되는 경우 MFC는 이 중에서 좀더 효율적인 **::SQLSetPos**를 사용합니다.  
  
##  <a name="_core_availability_of_dynasets"></a> 다이너셋의 가용성  
 MFC 데이터베이스 클래스는 아래 요구 사항이 충족되면 다이너셋을 지원합니다.  
  
-   데이터 소스에 ODBC 커서 라이브러리 DLL을 사용하지 않아야 합니다.  
  
     커서 라이브러리를 사용하면 다이너셋 지원에 필수적인 내부 ODBC 드라이버의 일부 기능이 방해를 받습니다.  다이너셋을 사용하려는 경우 이 절의 나머지 부분에서 설명하듯이 ODBC 드라이버가 다이너셋에 필요한 모든 기능을 가지고 있으면 `CDatabase` 개체를 만들 때 MFC에서 커서 라이브러리를 로드하지 않도록 할 수 있습니다.  자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 `CDatabase` 클래스의 [OpenEx](../Topic/CDatabase::OpenEx.md) 또는 [Open](../Topic/CDatabase::Open.md) 멤버 함수를 참조하십시오.  
  
     ODBC 용어로 다이너셋과 스냅샷을 커서라고 합니다.  커서는 레코드 집합에서 위치를 추적하는 데 사용되는 메커니즘입니다.  
  
-   데이터 소스를 위한 ODBC 드라이버는 키 집합 구동 커서를 지원해야 합니다.  
  
     키 집합 구동 커서는 키 집합을 가져오고 저장하여 테이블에서 데이터를 관리합니다.  키는 사용자가 특정 레코드로 스크롤할 때 테이블의 현재 데이터를 가져오는 데 사용됩니다.  드라이버가 이 기능을 지원하는지 여부를 알려면 **SQL\_SCROLL\_OPTIONS** 매개 변수를 사용하여 **::SQLGetInfo** ODBC API 함수를 호출하십시오.  
  
     키 집합 지원 기능을 사용하지 않고 다이너셋을 열려고 하면 **AFX\_SQL\_ERROR\_DYNASET\_NOT\_SUPPORTED** 반환 코드 값과 함께 `CDBException`이 발생합니다.  
  
-   해당 데이터 소스에 대한 ODBC 드라이버가 확장 페치를 지원해야 합니다.  
  
     확장 페치는 SQL 쿼리의 결과 레코드에서 앞과 뒤로 스크롤하는 기능입니다.  드라이버가 이 기능을 지원하는지 여부를 알려면 **SQL\_API\_SQLEXTENDEDFETCH** 매개 변수를 사용하여 **::SQLGetFunctions** ODBC API 함수를 호출하십시오.  
  
 업데이트 가능한 다이너셋이나 스냅샷을 사용하려면 ODBC 드라이버가 **::SQLSetPos** ODBC API 함수 또는 위치 지정 업데이트를 지원해야 합니다.  **::SQLSetPos** 함수를 사용하면 MFC에서 SQL 문을 보내지 않고 데이터 소스를 업데이트할 수 있습니다.  이 지원 기능이 제공되는 경우 MFC는 SQL을 통해 업데이트하기 위해 이를 우선적으로 사용합니다.  드라이버가 **::SQLSetPos**를 지원하는지 여부를 알려면 **SQL\_POS\_OPERATIONS** 매개 변수를 사용하여 **::SQLGetInfo**를 호출하십시오.  
  
 위치 지정 업데이트는 **WHERE CURRENT OF** \<커서이름\> 형식의 SQL 구문을 사용하여 데이터 소스의 테이블에서 특정 행을 식별합니다.  드라이버가 위치 지정 업데이트를 지원하는지 여부를 알려면 **SQL\_POSITIONED\_STATEMENTS** 매개 변수를 사용하여 **::SQLGetInfo**를 호출하십시오.  
  
 일반적으로 MFC 다이너셋\(앞으로만 이동 가능한 레코드 집합은 제외\)을 사용하려면 수준 2 API 규칙을 따르는 ODBC 드라이버가 필요합니다.  데이터 소스용 드라이버가 수준 1 API 규칙을 따르는 경우 업데이트 가능하고 읽기 전용인 스냅샷과 앞으로만 이동 가능한 레코드 집합 모두를 사용할 수 있지만 다이너셋은 사용할 수 없습니다.  그러나 확장 페치 및 키 집합 구동 커서를 지원하는 경우에는 수준 1 드라이버로 다이너셋을 사용할 수 있습니다.  ODBC 규칙 수준에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)를 참조하십시오.  
  
> [!NOTE]
>  스냅숏과 다이너셋 모두를 사용하려면 드라이버가 서로 다른 두 개의 `CDatabase` 개체\(서로 다른 두 개의 연결\)에 기초해야 합니다.  
  
 ODBC 커서 라이브러리에서 관리하는 중간 저장소를 사용하는 스냅샷과 달리 다이너셋은 스크롤하는 즉시 데이터 소스에서 직접 레코드를 페치합니다.  이렇게 하면 다이너셋에서 선택한 원래 레코드가 데이터 소스와 동기화됩니다.  
  
 이 버전의 Visual C\+\+에 포함된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대한 내용은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)