---
title: "스냅샷 | Microsoft Docs"
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
  - "커서 라이브러리[ODBC], 스냅샷"
  - "커서[ODBC], static"
  - "ODBC 커서 라이브러리[ODBC], 스냅샷"
  - "ODBC 레코드 집합, 스냅샷"
  - "레코드 집합, 스냅샷"
  - "스냅샷"
  - "스냅샷, ODBC 지원"
  - "정적 커서"
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 스냅샷
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스냅숏은 생성 당시에 있던 그대로 데이터의 정적 뷰를 반영하는 레코드 집합입니다.  스냅숏을 열어 모든 레코드로 이동시키고 나면 스냅숏에 포함된 레코드 집합 및 값은 **Requery**를 호출하여 스냅숏을 다시 만들 때까지 변경되지 않습니다.  
  
> [!NOTE]
>  이 항목은 MFC ODBC 클래스에 적용됩니다.  MFC ODBC 클래스 대신 MFC DAO 클래스를 사용하는 경우에는 [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)에서 스냅숏 형식 레코드 집합에 대한 설명을 참조하십시오.  
  
 데이터베이스 클래스를 사용하여 업데이트 가능한 스냅숏 또는 읽기 전용 스냅숏을 만들 수 있습니다.  다이너셋과 달리 업데이트 가능한 스냅숏은 다른 사용자에 의한 레코드 값 변경을 반영하지 않지만 사용자 프로그램에서 수행한 업데이트나 삭제는 반영합니다.  스냅숏에 추가한 레코드는 **Requery**를 호출하기 전에는 스냅숏에 나타나지 않습니다.  
  
> [!TIP]
>  스냅숏은 ODBC 정적 커서입니다.  정적 커서는 해당 레코드로 스크롤하기 전에는 실제로 데이터 행을 가져오지 않습니다.  모든 레코드를 즉시 검색하려면 레코드 집합의 마지막 레코드까지 스크롤한 다음 보려는 첫째 레코드로 스크롤하십시오.  그러나 마지막 레코드까지 스크롤하면 추가 오버헤드로 인해 성능이 저하될 수 있습니다.  
  
 스냅숏은 보고서를 작성하거나 계산을 수행할 때처럼 작업을 하는 동안 데이터가 고정되어 있어야 하는 경우에 유용합니다.  이 경우에도 시간이 지나면 데이터 소스가 스냅숏과 많이 달라질 수 있으므로 가끔씩 스냅숏을 다시 만드는 것이 좋습니다.  
  
 스냅숏 지원은 모든 수준 1 드라이버에 정적 커서 및 위치 지정 업데이트\(업데이트 시 필요\)를 제공하는 ODBC 커서 라이브러리를 기반으로 합니다.  이 지원을 위해 커서 라이브러리 DLL을 메모리에 로드해야 합니다.  `CDatabase` 개체를 생성하고 `OpenEx` 멤버 함수를 호출하는 경우 `dwOptions` 매개 변수의 **CDatabase::useCursorLib** 옵션을 지정해야 합니다.  **Open** 멤버 함수를 호출하면 커서 라이브러리가 기본적으로 로드됩니다.  스냅숏 대신 다이너셋을 사용할 때는 커서 라이브러리를 로드하지 않는 것이 좋습니다.  
  
 `CDatabase` 개체가 생성될 당시 ODBC 커서 라이브러리가 로드되었거나 사용 중인 ODBC 드라이버가 정적 커서를 지원하는 경우에만 스냅숏을 사용할 수 있습니다.  
  
> [!NOTE]
>  일부 ODBC 드라이버에서는 스냅숏\(정적 커서\)을 업데이트하지 못할 수도 있습니다.  지원되는 커서 형식과 동시성 형식을 드라이버 설명서에서 확인하십시오.  스냅숏을 업데이트할 수 있으려면 `CDatabase` 개체를 만들 때 메모리에 커서 라이브러리를 로드해야 합니다.  자세한 내용은 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)를 참조하십시오.  
  
> [!NOTE]
>  스냅숏과 다이너셋 모두를 사용하려면 드라이버가 서로 다른 두 개의 `CDatabase` 개체\(서로 다른 두 개의 연결\)에 기초해야 합니다.  
  
 스냅숏이 모든 레코드 집합과 공유하는 속성에 대한 자세한 내용은 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)을 참조하십시오.  ODBC 커서 라이브러리를 비롯하여 ODBC와 스냅숏에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)를 참조하십시오.  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)