---
title: "ODBC 관리자 | Microsoft Docs"
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
  - "ODBC 관리자 관리"
  - "ODBC에서 관리자"
  - "드라이버[C++], ODBC"
  - "ODBC 설치"
  - "ODBC[C++], ODBC 관리자"
  - "ODBC 관리자[C++]"
  - "ODBC 데이터 소스[C++], ODBC 관리자"
  - "ODBC 드라이버[C++], 설치"
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ODBC 관리자
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC 관리자는 로컬이나 네트워크에서 사용할 수 있도록 [데이터 소스](../../data/odbc/data-source-odbc.md)를 등록하고 구성합니다.  마법사는 ODBC 관리자가 제공하는 정보를 사용하여 사용자를 데이터 소스에 연결하기 위한 코드를 응용 프로그램에 작성합니다.  
  
 MFC ODBC 클래스 또는 MFC DAO\(데이터 액세스 개체\) 클래스를 통해 사용할 수 있도록 ODBC 데이터 소스를 설정하려면 먼저 데이터 소스를 등록하고 구성해야 합니다.  데이터 소스를 추가하거나 제거하려면 ODBC 관리자를 사용합니다.  ODBC 드라이버에 따라서는 새 데이터 소스를 만들 수도 있습니다.  
  
 ODBC 관리자는 설치 프로그램을 실행하는 동안 설치됩니다.  **사용자 지정** 설치를 선택하고 **데이터베이스 옵션** 대화 상자에서 ODBC 드라이버를 선택하지 않은 경우 필요한 파일을 설치하려면 설치 프로그램을 다시 실행해야 합니다.  
  
 설치 프로그램을 실행하는 동안 설치하려는 ODBC 드라이버를 선택하십시오.  나중에 Visual C\+\+ 설치 프로그램을 사용하여 Visual C\+\+에 제공되는 추가 드라이버를 설치할 수 있습니다.  
  
 Visual C\+\+에 제공되지 않은 ODBC 드라이버를 설치하려면 해당 드라이버를 포함하는 설치 프로그램을 실행해야 합니다.  
  
#### Visual C\+\+에 제공되는 ODBC 드라이버를 설치하려면  
  
1.  Visual C\+\+ 배포 CD에서 설치 프로그램을 실행합니다.  
  
     설치 프로그램에서 열기 대화 상자가 나타납니다.  
  
2.  **설치 옵션** 대화 상자가 나타날 때까지 각 대화 상자에서 **다음**을 클릭합니다.  **사용자 지정**을 선택한 다음 `Next`를 클릭합니다.  
  
3.  **Microsoft Visual C\+\+ 설치** 대화 상자에서 **데이터베이스 옵션** 확인란을 제외한 모든 확인란을 선택 해제한 다음 **자세히**를 클릭하여 **데이터베이스 옵션** 대화 상자를 표시합니다.  
  
4.  **Microsoft Data Access Objects** 확인란을 해제하고 **Microsoft ODBC 드라이버** 확인란을 선택하고 **자세히**를 클릭합니다.  
  
     **Microsoft ODBC 드라이버** 대화 상자가 나타납니다.  
  
5.  설치할 드라이버를 선택하고 **확인**을 두 번 클릭합니다.  
  
6.  나머지 대화 상자에서 **다음**을 클릭하여 설치를 시작합니다.  설치가 완료되면 메시지가 나타납니다.  
  
 드라이버를 설치하고 나면 ODBC 관리자를 사용하여 데이터 소스를 구성할 수 있습니다.  제어판에서 ODBC 아이콘을 찾을 수 있습니다.  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md)