---
title: "MFC 데이터베이스 프로그래밍 모델은 무엇입니까? | Microsoft Docs"
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
  - "DAO[C++], MFC"
  - "데이터 액세스[C++], 기술"
  - "데이터베이스[C++], MFC"
  - "MFC[C++], 데이터베이스 응용 프로그램"
  - "ODBC[C++], MFC"
  - "ODBC 클래스[C++], MFC 데이터베이스 클래스"
ms.assetid: f6f15bb8-4115-41f2-ad68-036e74a11bd9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 데이터베이스 프로그래밍 모델은 무엇입니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC가 DAO와 ODBC를 구현하는 방법은 기본적으로 아주 다르지만 인터페이스는 서로 비슷하므로 비교적 쉽게 양자 간에, 특히 ODBC에서 DAO로 응용 프로그램을 이식할 수 있습니다.  ODBC에서 DAO로 이식하는 데 대한 자세한 내용은 [Technical Note 55](../mfc/tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes.md)를 참조하십시오.  뿐만 아니라 MFC의 DAO 및 ODBC 인터페이스는 Visual Basic의 DAO 및 ODBC 인터페이스와 아주 비슷합니다.  
  
 MFC 프로그래밍 모델은 각 개방형 데이터베이스에 데이터베이스 개체를 제공하고,  데이터베이스 개체는 데이터베이스로의 연결을 나타냅니다.  쿼리와 업데이트는 레코드 집합 개체를 통해 실행합니다.  DAO는 테이블 구조 작업 및 다시 사용할 수 있도록 쿼리를 저장하기 위한 추가 개체를 제공합니다. 이 내용은 나중에 자세히 설명합니다.  MFC는 이러한 각 DAO 개체와 ODBC 개체에 클래스 집합을 하나씩 제공합니다.  
  
 MFC를 사용하여 데이터를 더 쉽게 액세스할 수 있습니다.  DAO와 ODBC 데이터베이스 클래스는 고수준의 추상화를 제공하므로 직접 DAO나 ODBC를 사용하지 않아도 됩니다.  해당 API에 작성하면 MFC 클래스를 사용할 때보다 작업이 복잡해집니다.  특히 비교적 단순하고 작은 응용 프로그램을 만들 때 그렇습니다.  
  
 데이터베이스 클래스는 MFC 클래스 라이브러리에 다음 구성 요소를 추가합니다.  
  
-   DAO나 ODBC를 통해 데이터베이스에 액세스하기 위한 고수준의 API를 제공하는 C\+\+ 데이터베이스 클래스  
  
-   응용 프로그램별 데이터베이스 클래스를 만드는 응용 프로그램 마법사와 **클래스 추가**에 대한 확장  
  
-   클래스와 마법사의 사용을 보여 주는 샘플 프로그램  
  
-   개요, 프로그래밍 항목에 대한 문서 및 클래스 참조 자료가 들어 있는 온라인 설명서  
  
 이들 구성 요소에 대한 자세한 내용은 [ODBC와 MFC](../data/odbc/odbc-and-mfc.md)를 참조하십시오.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [DAO와 ODBC 사이에서 선택](../data/should-i-use-dao-or-odbc-q.md)  
  
-   DAO 및 ODBC의 [DDL과 DML이 지원됩니까?](../data/are-ddl-and-dml-supported-q.md)  
  
-   [MFC 데이터베이스 지원 설치](../data/installing-mfc-database-support.md)  
  
-   MFC의 [ODBC](../data/odbc/odbc-and-mfc.md) 클래스  
  
-   [MFC 데이터 액세스 프로그래밍 문서](../data/mfc-database-documentation.md)  
  
-   [MFC의 ODBC 구현 방법](../data/odbc/odbc-and-mfc.md)  
  
## 참고 항목  
 [데이터 액세스에 대한 질문과 대답](../data/data-access-frequently-asked-questions-mfc-data-access.md)