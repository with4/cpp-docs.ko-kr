---
title: "데이터 소스(ODBC) | Microsoft Docs"
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
  - "CDatabase 클래스, 데이터 소스 연결"
  - "ODBC 데이터 소스 구성"
  - "ODBC 데이터 소스"
  - "ODBC 데이터 소스, 구성"
  - "ODBC 데이터 소스, CDatabase에서 표시"
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 데이터 소스(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 데이터베이스 용어로 데이터 소스는 데이터, 데이터에 액세스하는 데 필요한 정보, 데이터 소스 이름으로 표시할 수 있는 데이터 소스 위치 등으로 구성된 특정 집합입니다.  [CDatabase](../../mfc/reference/cdatabase-class.md) 클래스를 사용하여 작업하려면 데이터 소스가 ODBC\(Open Database Connectivity\) 관리자를 사용하여 구성된 것이여야 합니다.  데이터 소스의 예로는 네트워크를 통해 Microsoft SQL Server에서 실행하는 원격 데이터베이스 또는 로컬 디렉터리의 Microsoft Access 파일이 있습니다.  해당 ODBC 드라이버가 있으면 응용 프로그램을 통해 데이터 소스에 액세스할 수 있습니다.  
  
 각기 `CDatabase` 개체로 표시되는 하나 이상의 데이터 소스를 응용 프로그램에서 활성화시킬 수 있습니다.  또한 데이터 소스에 대해 동시에 다중 연결을 설정할 수도 있습니다.  설치한 드라이버와 ODBC 드라이버의 기능에 따라 로컬 데이터 소스뿐 아니라 원격 데이터 소스에도 연결할 수 있습니다.  데이터 소스와 ODBC 관리자에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 [ODBC 관리자](../../data/odbc/odbc-administrator.md)를 참조하십시오.  
  
 다음 항목에서는 데이터 소스에 대한 추가 정보를 제공합니다.  
  
-   [데이터 소스: 연결 관리\(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [데이터 소스: 데이터 소스의 스키마 확인\(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)