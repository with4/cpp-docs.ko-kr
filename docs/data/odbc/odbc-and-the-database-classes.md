---
title: "ODBC 및 데이터베이스 클래스 | Microsoft Docs"
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
  - "데이터베이스 클래스[C++], ODBC"
  - "MFC[C++], ODBC 및"
  - "ODBC API 함수[C++]"
  - "ODBC 클래스[C++], MFC 데이터베이스 클래스"
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC 및 데이터베이스 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ODBC 데이터베이스 클래스는 일반적으로 [CDatabase](../../mfc/reference/cdatabase-class.md) 및[CRecordset](../../mfc/reference/crecordset-class.md) 클래스의 멤버 함수에서 프로그래머가 직접 만들어야 하는 ODBC API 함수 호출을 캡슐화합니다.  예를 들어 복잡한 ODBC 호출 시퀀스, 반환되는 레코드를 저장 위치에 바인딩하는 작업, 오류 조건 처리 및 기타 작업을 데이터베이스 클래스가 대신 관리하므로  프로그래머는 훨씬 단순한 클래스 인터페이스를 사용하여 레코드 집합 개체를 통해 레코드를 조작할 수 있습니다.  
  
> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC DAO\(데이터 액세스 개체\) 클래스를 통해서도 액세스할 수 있습니다.  
  
 데이터베이스 클래스는 ODBC 기능을 캡슐화하지만 ODBC API 함수와의 일대일 매핑을 제공하지는 않습니다.  데이터베이스 클래스는 Microsoft Access 및 Microsoft Visual Basic에서 사용하는 데이터 액세스 개체 모델을 따르는 높은 수준의 추상화를 제공합니다.  자세한 내용은 [MFC 데이터베이스 프로그래밍 모델은 무엇입니까?](../../data/what-is-the-mfc-database-programming-model-q.md)를 참조하십시오.  
  
## 참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)