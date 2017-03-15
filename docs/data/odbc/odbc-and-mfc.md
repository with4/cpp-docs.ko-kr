---
title: "ODBC 및 MFC | Microsoft Docs"
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
  - "연결[C++], 데이터 소스"
  - "연결[C++], 데이터베이스"
  - "데이터 소스[C++], 연결"
  - "데이터베이스 연결[C++], MFC ODBC 클래스"
  - "데이터베이스[C++], 연결"
  - "MFC[C++], ODBC 및"
  - "ODBC[C++], MFC"
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ODBC 및 MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Windows NT 등의 Win32 플랫폼에서 MFC 데이터베이스 클래스를 사용하려면 데이터 소스에 맞는 ODBC 드라이버가 있어야 합니다.  일부 드라이버는 Visual C\+\+에 포함되어 있으며 다른 드라이버는 Microsoft나 다른 공급업체에서 구할 수 있습니다.  자세한 내용은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
 이 항목에서는 MFC\(Microsoft Foundation Class\) 라이브러리의 ODBC 기반 데이터베이스 클래스의 기본 개념을 소개하고 이들 클래스가 함께 작동하는 원리에 대한 개요를 제공합니다.  ODBC와 MFC에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [데이터 소스에 연결](../../data/odbc/connecting-to-a-data-source.md)  
  
-   [레코드 선택 및 조작](../../data/odbc/selecting-and-manipulating-records.md)  
  
-   [폼에서 데이터의 표시와 조작](../../data/odbc/displaying-and-manipulating-data-in-a-form.md)  
  
-   [문서 및 뷰 작업](../../data/odbc/working-with-documents-and-views.md)  
  
-   [ODBC 및 SQL 액세스](../../data/odbc/access-to-odbc-and-sql.md)  
  
-   [MFC ODBC 클래스에 대한 추가 정보](../../data/odbc/further-reading-about-the-mfc-odbc-classes.md)  
  
 ODBC 기반 MFC 데이터베이스 클래스는 사용 가능한 ODBC 드라이버가 있는 모든 데이터베이스에 액세스할 수 있도록 디자인되었습니다.  클래스가 ODBC를 사용하기 때문에 응용 프로그램은 다양한 형식의 데이터 및 서로 다른 로컬\/원격 구성에 있는 데이터에 액세스할 수 있습니다.  서로 다른 DBMS\(데이터베이스 관리 시스템\)를 처리하기 위해 코드를 따로 작성할 필요가 없습니다.  액세스할 데이터에 맞는 ODBC 드라이버를 갖춘 사용자는 프로그램을 사용하여 해당 DBMS에 저장된 테이블의 데이터를 조작할 수 있습니다.  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)