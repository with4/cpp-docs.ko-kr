---
title: "다이너셋에 대한 ODBC 드라이버 요구 사항 | Microsoft Docs"
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
  - "드라이버, 다이너셋"
  - "드라이버, ODBC"
  - "다이너셋"
  - "ODBC 드라이버, 다이너셋"
  - "ODBC 레코드 집합, 다이너셋"
  - "레코드 집합, 다이너셋"
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 다이너셋에 대한 ODBC 드라이버 요구 사항
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ODBC 데이터베이스 클래스에서 다이너셋은 동적 속성을 가진 레코드 집합이며 특정 방법으로 데이터 소스와 항상 동기화됩니다.  MFC 다이너셋\(앞으로만 이동 가능한 레코드 집합은 제외\)을 사용하려면 수준 2 API 규칙을 따르는 ODBC 드라이버가 필요합니다.  [데이터 소스](../../data/odbc/data-source-odbc.md)용 드라이버가 수준 1 API 집합을 따르는 경우 업데이트 가능하고 읽기 전용인 스냅샷과 앞으로만 이동 가능한 레코드 집합을 둘 다 사용할 수 있지만 다이너셋은 사용할 수 없습니다.  그러나 수준 1 드라이버에서 확장 페치 및 키 집합 구동 커서를 지원하는 경우에는 다이너셋이 지원됩니다.  
  
 ODBC 용어로 다이너셋과 스냅샷을 커서라고 합니다.  커서는 레코드 집합에서 위치를 추적하는 데 사용되는 메커니즘입니다.  다이너셋에 대한 드라이버 요구 사항에 대한 자세한 내용은 [다이너셋](../../data/odbc/dynaset.md)을 참조하십시오.  커서에 대한 자세한 내용은 MSDN 설명서에서 [ODBC\(Open Database Connectivity\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK를 참조하십시오.  
  
> [!NOTE]
>  업데이트 가능한 레코드 집합을 사용하려면 ODBC 드라이버가 위치 지정 업데이트 문이나 **::SQLSetPos** ODBC API 함수를 지원해야 합니다.  둘 다 지원되는 경우 MFC는 이 중에서 좀더 효율적인 **::SQLSetPos**를 사용합니다.  스냅샷을 위해 커서 라이브러리를 사용할 수도 있습니다. 커서 라이브러리는 업데이트 가능한 스냅샷에 필요한 지원 기능\(정적 커서 및 위치 지정 업데이트 문\)을 제공합니다.  
  
## 참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)