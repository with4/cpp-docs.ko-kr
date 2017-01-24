---
title: "ODBC: ODBC 데이터 소스 구성 | Microsoft Docs"
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
  - "ODBC 데이터 소스 구성"
  - "ODBC 연결, 구성"
  - "ODBC 데이터 소스, 구성"
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC: ODBC 데이터 소스 구성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개발한 응용 프로그램에서 [데이터 소스](../../data/odbc/data-source-odbc.md)를 사용하려면 ODBC 관리자를 사용하여 데이터 소스를 구성해야 합니다.  ODBC 관리자는 사용 가능한 데이터 소스 및 연결 정보를 Windows 레지스트리를 통해 추적합니다.  ODBC 관리자를 사용하여 **데이터 소스** 대화 상자에서 데이터 소스를 추가, 수정 및 삭제하고 ODBC 드라이버를 추가하거나 삭제할 수 있습니다.  
  
> [!NOTE]
>  이 내용은 ODBC 액세스를 위해 MFC DAO\(데이터 액세스 개체\) 클래스를 사용하거나 MFC ODBC 클래스를 사용하는 경우에 적용됩니다.  
  
 ODBC 관리자는 MFC\(Microsoft Foundation Class\) 라이브러리 데이터베이스 지원 기능과 함께 자동 설치됩니다.  ODBC 관리자 프로그램에 대한 자세한 내용은 [ODBC 관리자](../../data/odbc/odbc-administrator.md) 및 ODBC API 참조 온라인 도움말 시스템을 참조하십시오.  
  
 MFC 데이터베이스 응용 프로그램을 위한 ODBC 설치 프로그램 및 관리 프로그램을 만드는 방법에 대한 자세한 내용은 [Technical Note 48](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)   
 [ODBC: ODBC API 함수 직접 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)