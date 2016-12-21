---
title: "데이터베이스 지원 설치 (MFC/ATL) | Microsoft Docs"
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
  - "ATL[C++], 데이터베이스 지원"
  - "데이터 액세스[C++], 데이터베이스 지원 설치"
  - "데이터베이스[C++], 데이터베이스 지원 설치"
  - "데이터베이스 지원 설치"
ms.assetid: 3820ba96-4fb8-4405-83dd-bb3bc5998667
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터베이스 지원 설치 (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ .NET 설치 프로그램을 실행하면 다음 데이터베이스 구성 요소가 자동으로 설치됩니다.  
  
-   필요한 모든 ATL OLE DB 구성 요소.  자세한 내용은 [ATL 데이터베이스 지원 설치](../data/installing-atl-database-support.md)를 참조하세요.  
  
-   ODBC 드라이버 관리자 및 ODBC 관리자 프로그램이 포함된 ODBC 드라이버 집합.  자세한 내용은 [MFC 데이터베이스 지원 설치](../data/installing-mfc-database-support.md)에서 "ODBC 드라이버 설치" 및 "ODBC SDK 구성 요소 설치"를 참조하세요.  
  
-   DAO SDK\(소프트웨어 개발 키트\)의 필요한 구성 요소.  여기에는 이 설명서에 통합되어 있지 않은 도움말 파일이 포함됩니다.  그러나 DAO를 사용하는 경우 운영 체제와 호환되는 Jet 버전을 설치해야 합니다.  자세한 내용은 [MFC 데이터베이스 지원 설치](../data/installing-mfc-database-support.md)dptj "DAO SDK 구성 요소 설치"를 참조하세요.  
  
 초기 설치의 일부로 Visual C\+\+ .NET에서 데이터 액세스 프로그래밍을 지원하는 데 필요한 MDAC\(Microsoft Data Access Components\)도 설치됩니다.  
  
 Visual C\+\+ .NET은 MDAC 2.7 SDK를 설치합니다.  Microsoft Universal Data Access 웹 사이트\([http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548)\)에서 MDAC SDK에 대한 업데이트와 새로운 소식을 확인해야 합니다.  
  
 데이터 액세스 응용 프로그램을 재배포하려면 MDAC 2.7 재배포 프로그램도 필요합니다.  MDAC 2.7 SDK는 Visual Studio .NET 필수 구성 요소 CD\-ROM의 MDAC 디렉터리에 포함된 MDAC 2.7 재배포 프로그램 \(Mdac\_typ.exe\)과 함께 사용해야 합니다.  위에 나와 있는 MDAC 2.7 SDK 다운로드 링크에서 Mdac\_typ.exe를 다운로드할 수도 있습니다.  구성 요소 재배포에 대한 자세한 내용은 [컨트롤 재배포](../data/ado-rdo/redistributing-controls.md)를 참조하세요.  
  
## 참고 항목  
 [데이터 액세스](../Topic/Data%20Access%20in%20Visual%20C++.md)