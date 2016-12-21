---
title: "데이터 소스: ODBC 데이터 소스에서 프로그래밍 방식으로 테이블 작성 | Microsoft Docs"
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
  - "ODBC 데이터 소스, 테이블 만들기"
  - "ODBC 테이블 프로그래밍 방식으로 만들기[C++]"
  - "테이블[C++]"
  - "테이블[C++], 프로그래밍 방식으로 만들기"
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 소스: ODBC 데이터 소스에서 프로그래밍 방식으로 테이블 작성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 `CDatabase` 클래스의 `ExecuteSQL` 멤버 함수를 사용하고 **CREATE TABLE** SQL 문을 포함하는 문자열을 함수에 전달하여 데이터 소스에 대한 테이블 만드는 방법에 대해 설명합니다.  
  
 MFC의 ODBC 데이터 소스에 대한 일반 정보는 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md)를 참조하십시오.  [데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md)에서는 데이터 소스를 만드는 방법에 대해 설명합니다.  
  
 데이터 소스를 설정하고 나면 `ExecuteSQL` 멤버 함수와 **CREATE TABLE** SQL 문을 사용하여 쉽게 테이블을 만들 수 있습니다.  예를 들어 `myDB`라는 `CDatabase` 개체가 있으면 다음 MFC 코드를 사용하여 테이블을 만들 수 있습니다.  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 이 코드 예제는 `myDB`에 의해 유지되는 Microsoft Access 데이터 소스 연결에서 "OFFICES"라는 테이블을 만듭니다. 이 테이블에는 "OfficeID"와 "OfficeName"의 두 개의 필드가 포함됩니다.  
  
> [!NOTE]
>  **CREATE TABLE** SQL 문에 지정되는 필드 형식은 사용하는 ODBC 드라이버에 따라 다를 수 있습니다.  Visual C\+\+ 1.5와 함께 배포되는 Microsoft Query 프로그램을 사용하면 데이터 소스에 대해 사용할 수 있는 필드 형식을 알 수 있습니다.  Microsoft Query에서 **파일**을 클릭하고 **테이블 정의**를 클릭한 후 데이터 소스에서 테이블을 선택하면 **형식** 콤보 상자에 필드 형식이 표시됩니다.  인덱스를 작성하기 위한 SQL 구문도 있습니다.  
  
## 참고 항목  
 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md)