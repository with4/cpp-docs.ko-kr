---
title: "고객에게 ODBC 구성 요소 재배포 | Microsoft Docs"
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
  - "구성 요소[C++]"
  - "구성 요소[C++], 배포"
  - "구성 요소[C++], 재배포"
  - "ODBC 관리자"
  - "ODBC 구성 요소, 재배포"
  - "ODBC, 분산 구성 요소"
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 고객에게 ODBC 구성 요소 재배포
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램에 ODBC 관리자 프로그램의 기능이 포함된 경우에는 이러한 프로그램을 실행시킬 수 있는 파일을 사용자에게 함께 배포해야 합니다.  이 ODBC 파일은 Visual C\+\+ CD\-ROM의 \\OS\\System 디렉터리에 있습니다.  이 디렉터리의 Redistrb.wri 파일과 사용권 계약에 재배포할 수 있는 ODBC 파일 목록이 있습니다.  
  
 배포할 ODBC 드라이버에 대해서는 설명서를 참조하여  배포할 DLL 및 기타 파일을 결정해야 합니다.  
  
 ODBC 구성 요소 및 드라이버에 대한 정보는 [데이터베이스 지원 설치](../../data/installing-database-support-mfc-atl.md)를 참조하고 ActiveX 컨트롤 재배포에 대한 내용은 [컨트롤 재배포](../../data/ado-rdo/redistributing-controls.md)를 참조하십시오.  
  
 대개의 경우 또 다른 파일을 하나 더 추가해야 합니다.  Odbccr32.dll은 ODBC 커서 라이브러리입니다.  이 라이브러리는 수준 1 드라이버에 앞과 뒤로 스크롤할 수 있는 기능을 제공하며  스냅숏 지원 기능도 제공합니다.  ODBC 커서 라이브러리에 대한 자세한 내용은 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)를 참조하십시오.  
  
 다음 항목에서 데이터베이스 클래스와 함께 ODBC를 사용하는 방법에 대한 자세한 내용을 참조하십시오.  
  
-   [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: ODBC 데이터 소스 구성](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: ODBC API 함수 직접 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## 참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)   
 [ODBC 관리자](../../data/odbc/odbc-administrator.md)