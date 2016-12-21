---
title: "DDL과 DML이 지원됩니까? | Microsoft Docs"
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
  - "MFC ODBC의 데이터 조작 언어[C++]"
  - "데이터베이스[C++], DAO에서 액세스"
  - "데이터베이스[C++], DDL 액세스"
  - "데이터베이스[C++], DML 액세스"
  - "DDLs[C++], MFC 지원"
  - "DML[C++]"
  - "DML[C++], MFC ODBC"
ms.assetid: 07f96d81-78d4-4bec-9138-b15d68fd5ce0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DDL과 DML이 지원됩니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC DAO 클래스는 다음 두 종류의 데이터베이스 액세스를 지원합니다.  
  
-   **DDL\(데이터 정의 언어\)** 데이터베이스를 만들거나 삭제하고, 테이블을 만들거나 삭제하고, 테이블 필드와 인덱스를 정의하고, 데이터베이스 구조에 영향을 주는 기타 작업을 할 수 있습니다.  
  
-   **DML\(데이터 조작 언어\)** 쿼리를 실행하고, 레코드를 추가, 삭제, 편집하거나 데이터베이스의 내용을 조작합니다.  
  
 MFC ODBC 클래스는 DML만 지원하지만 직접 ODBC API 함수를 호출하여 DDL 작업을 수행할 수 있습니다.  
  
## 참고 항목  
 [데이터 액세스에 대한 질문과 대답](../data/data-access-frequently-asked-questions-mfc-data-access.md)