---
title: "레코드 선택 및 조작 | Microsoft Docs"
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
  - "ODBC 레코드 집합, 레코드 선택"
  - "레코드 선택, MFC ODBC 클래스"
  - "레코드, 선택"
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 레코드 선택 및 조작
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적으로 SQL **SELECT** 문을 사용하여 데이터 소스에서 레코드를 선택하면 테이블 또는 쿼리에서 선택된 레코드 집합인 결과 집합을 얻게 됩니다.  데이터베이스 클래스를 사용할 때는 레코드 집합 개체를 통해 결과 집합을 선택하고 액세스합니다.  이 개체는 [CRecordset](../../mfc/reference/crecordset-class.md) 클래스에서 파생되는 특정 응용 프로그램별 클래스 개체입니다.  레코드 집합 클래스를 정의할 때는 클래스와 연결할 데이터 소스, 사용할 테이블, 테이블의 열을 지정합니다.  MFC 응용 프로그램 마법사나 **클래스 추가**\([MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)의 설명 참조\)를 사용하면 특정 데이터 소스와 연결된 클래스가 생성됩니다.  마법사는 테이블 이름을 반환하는 `CRecordset` 클래스의 [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md) 멤버 함수를 작성합니다.  마법사를 사용하여 레코드 집합 클래스를 작성하는 방법에 대한 자세한 내용은 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md) 및 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 참조하십시오.  
  
 런타임에 [CRecordset](../../mfc/reference/crecordset-class.md) 개체를 사용하여 다음과 같은 작업을 수행할 수 있습니다.  
  
-   현재 레코드의 데이터 필드 검사  
  
-   레코드 집합 필터링 또는 정렬  
  
-   기본 SQL **SELECT** 문 사용자 지정  
  
-   선택한 레코드에서 스크롤  
  
-   레코드 추가, 업데이트 또는 삭제\(데이터 소스와 레코드 집합 모두 업데이트 가능한 경우\)  
  
-   레코드 집합을 다시 퀴리할 수 있는지 여부를 테스트하고 레코드 집합의 내용 새로 고침  
  
 레코드 집합 개체의 사용을 마치면 개체를 닫거나 삭제합니다.  레코드 집합에 대한 자세한 내용은 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)