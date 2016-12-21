---
title: "MFC 데이터베이스 지원 설치 | Microsoft Docs"
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
  - "DAO[C++], 구성 요소 설치"
  - "데이터베이스[C++], 데이터베이스 지원 설치"
  - "데이터베이스[C++], MFC"
  - "DAO 설치"
  - "ODBC 설치"
  - "ODBC 구성 요소[C++], 설치"
  - "ODBC 드라이버[C++], 설치"
ms.assetid: a6c2fc84-9e0e-4f39-a464-0bcbc415b946
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 데이터베이스 지원 설치
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

##  <a name="_core_odbc_drivers_installed"></a> ODBC 드라이버 설치  
 설치되는 ODBC 드라이버는 다음과 같습니다.  
  
-   Microsoft Access  
  
-   Microsoft dBASE 드라이버  
  
-   Microsoft Excel  
  
-   Microsoft FoxPro VFP 드라이버  
  
-   Microsoft Visual FoxPro 드라이버  
  
-   Microsoft ODBC for Oracle 드라이버  
  
-   Microsoft Paradox 드라이버  
  
-   Microsoft Text 드라이버  
  
-   Microsoft SQL Server 드라이버  
  
 이 버전의 Visual C\+\+에 포함된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대한 내용은 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
##  <a name="_core_odbc_sdk_components_installed"></a> ODBC SDK 구성 요소 설치  
 Visual C\+\+에는 필수 헤더 파일, 라이브러리, DLL 및 도구 등 중요한 여러 가지 ODBC 구성 요소가 들어 있습니다.  이러한 구성 요소 중에는 ODBC 데이터 소스를 구성하는 데 사용하는 ODBC 관리자 제어판 응용 프로그램 및 ODBC 드라이버 관리자가 포함되어 있습니다.  이외에도, [ODBC 드라이버 설치](#_core_odbc_drivers_installed)에 나와 있는 일반적으로 사용되는 여러 DBMS용 ODBC 드라이버가 포함되어 있습니다.  
  
 ODBC SDK는 ODBC 드라이버를 작성하고 테스트하는 데 필요한 추가 정보와 도구를 제공합니다.  단, Visual C\+\+ .NET의 경우에는 ODBC SDK가 Visual C\+\+ .NET 설치 미디어에 포함되어 있지 않고 Visual Studio .NET 필수 구성 요소로 설치된 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 일부로 포함되어 있습니다.  
  
##  <a name="_core_dao_sdk_components_installed"></a> DAO SDK 구성 요소 설치  
  
> [!NOTE]
>  새로운 프로젝트에는 OLE DB나 ODBC를 사용하는 것이 좋습니다.  DAO는 기존 응용 프로그램을 관리하는 경우에만 사용해야 합니다.  
  
 기본으로 설치되는 DAO SDK의 구성 요소는 다음과 같습니다.  
  
-   Microsoft Jet\(4.0 SP3\)  
  
-   Microsoft Jet\(3.x MDB\)  
  
-   Microsoft Jet\(1.x, 2.x\)  
  
-   [DAO와 ODBC를 사용하여 액세스할 수 있는 데이터 소스는 무엇입니까?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)에 나열된 모든 데이터베이스 형식  
  
 Visual C\+\+ .NET에서 DAO SDK는 Visual Studio .NET 필수 구성 요소로 설치됩니다.  \\Jet\\Jetsetup.exe를 실행합니다.  
  
> [!NOTE]
>  Jet 4.0 서비스 팩 3\(버전 2927.04\) 이상을 사용하는 것이 좋습니다.  Jet 4.0 서비스 팩 3은 Windows 2000 및 Windows ME와 함께 제공됩니다.  이 버전의 Jet 데이터베이스를 사용하면, 사용 중인 응용 프로그램으로 테스트해야 하는 Jet 버전의 수를 줄일 수 있습니다.  Windows XP에는 다른 버전의 Jet 데이터베이스가 제공될 수 있습니다.  [컨트롤 재배포](../data/ado-rdo/redistributing-controls.md)에 나와 있는 "Note on Redistributing DAO Components"를 참조하십시오.  
  
 DAO SDK C\+\+ 클래스, 예제 파일 또는 DAO 도움말 파일의Windows 도움말 버전 등 기타 DAO SDK 구성 요소를 설치하려면 Visual C\+\+ 6.0 CD\-ROM에 있는 DAO SDK를 설치합니다.  
  
 For updates to and news about OLE DB, see the Universal Data Access Web site at [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## 참고 항목  
 [데이터 엑세스 프로그래밍 \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)