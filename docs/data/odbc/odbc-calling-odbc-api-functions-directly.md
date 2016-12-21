---
title: "ODBC: ODBC API 함수 직접 호출 | Microsoft Docs"
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
  - "API[C++], 호출"
  - "카탈로그 함수(ODBC)"
  - "카탈로그 함수(ODBC), 호출"
  - "직접 ODBC API 호출"
  - "ODBC[C++], API 함수"
  - "ODBC[C++], 카탈로그 함수"
  - "ODBC API 함수[C++]"
  - "ODBC API 함수[C++], 호출"
  - "ODBC 클래스[C++], ODBC API와 비교"
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC: ODBC API 함수 직접 호출
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터베이스 클래스에서 [데이터 소스](../../data/odbc/data-source-odbc.md)에 제공하는 인터페이스는 ODBC에서 제공하는 것보다 단순합니다.  따라서 클래스에서 ODBC API의 모든 기능을 캡슐화하지 않습니다.  이 클래스에서 지원하지 않는 기능에 대해서는 ODBC API 함수를 직접 호출해야 합니다.  예를 들어 **::SQLColumns**, **::SQLProcedures**, **::SQLTables** 같은 ODBC 카탈로그 함수는 직접 호출되어야 합니다.  
  
> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC DAO\(데이터 액세스 개체\) 클래스를 통해서도 액세스할 수 있습니다.  
  
 ODBC API 함수를 직접 호출하려면 프레임워크를 사용하지 않고 호출할 때와 마찬가지로 아래와 같은 단계를  지정합니다.  
  
-   호출에서 반환되는 결과를 저장할 저장소를 할당합니다.  
  
-   함수의 매개 변수 시그니처에 따라 ODBC **HDBC** 또는 **HSTMT** 핸들을 전달합니다.  [AFXGetHENV](../Topic/AfxGetHENV.md) 매크로를 사용하여 ODBC 핸들을 검색합니다.  
  
     직접 할당하고 초기화할 필요 없이 멤버 변수 **CDatabase::m\_hdbc** 및 **CRecordset::m\_hstmt**를 사용할 수 있습니다.  
  
-   추가 ODBC 함수를 호출하여 주 호출을 준비하거나 주 호출의 후속 작업을 적절히 처리합니다.  
  
-   사용이 끝난 저장소의 할당을 취소합니다.  
  
 이들 단계에 대한 자세한 내용은 MSDN 설명서에서 [ODBC\(Open Database Connectivity\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK를 참조하십시오.  
  
 이러한 단계 외에 함수의 반환 값을 확인하고, 프로그램이 비동기 호출이 종료되는 것을 기다리고 있지 않은지 확인하고 기타 작업을 위한 추가 단계가 필요합니다.  이러한 최종 단계는 `AFX_SQL_ASYNC` 및 `AFX_SQL_SYNC` 매크로를 사용하여 간단히 수행할 수 있습니다.  자세한 내용은 MFC 참조의 [매크로 및 전역](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)