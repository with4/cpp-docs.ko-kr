---
title: 'TN048: MFC 데이터베이스 응용 프로그램에 대 한 ODBC 설정 및 관리 프로그램 작성 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.odbc
dev_langs:
- C++
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7d89b6c6e05a5baf973abace2c64de3b52754f5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954559"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: MFC 데이터베이스 응용 프로그램에 대한 ODBC 설정 및 관리 프로그램 작성
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 MFC 데이터베이스 클래스를 사용 하 여 응용 프로그램 설치 프로그램을 ODBC 구성 요소를 설치 해야 합니다. 사용 가능한 드라이버 기본 드라이버를 지정 하 고 데이터 원본을 구성 하는 방법에 대 한 정보를 검색 하는 ODBC 관리 프로그램을 할 수도 있습니다. 이 주석은 이러한 프로그램을 작성 하는 ODBC 설치 관리자 API의 사용을 설명 합니다.  
  
##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a> ODBC 설치 프로그램을 작성  
 MFC 데이터베이스 응용 프로그램 (ODBC ODBC 드라이버 관리자에 필요. DLL) 및 ODBC 드라이버를 데이터 원본에 가져올 수 있습니다. 대부분의 ODBC 드라이버는 추가 네트워크 및 통신 Dll도 필요합니다. 대부분의 ODBC 드라이버는 필요한 ODBC 구성 요소를 설치 하는 설치 프로그램으로 제공 됩니다. MFC 데이터베이스 클래스를 사용 하 여 응용 프로그램 개발자는 다음 작업을 수행할 수 있습니다.  
  
-   ODBC 구성 요소를 설치 하기 위한 드라이버 관련 설치 프로그램에 의존 합니다. 이 더 이상 작업이 필요 개발자의 부분에-방금 드라이버의 설치 프로그램을 재배포할 수 있습니다.  
  
-   또는 드라이버 관리자와 드라이버를 설치 하 여 직접 설치 프로그램을 작성할 수 있습니다.  
  
 응용 프로그램별 설치 프로그램을 작성 하는 ODBC 설치 관리자 API는 사용할 수 있습니다. ODBC 설치 DLL 설치 관리자 API의에서 함수 구현-ODBCINST 합니다. 16 비트 Windows 및 ODBCCP32에 대 한 DLL입니다. Win32 DLL입니다. 응용 프로그램에서 호출할 수 `SQLInstallODBC` 설치 관리자에서 ODBC 드라이버 관리자, ODBC 드라이버 및 설치 하는 DLL는 변환기가 필요 합니다. 다음은 ODBCINST에 설치 된 드라이버 및 번역기 기록합니다. INI 파일 (또는 nt 레지스트리). `SQLInstallODBC` ODBC에 대 한 전체 경로가 필요합니다. INF 파일 설치 되도록 드라이버 목록을 포함 하 고 각 드라이버를 구성 하는 파일에 설명 합니다. 또한 드라이버 관리자 및 변환기에 대 한 유사한 정보를 포함합니다. ODBC 합니다. INF 파일은 일반적으로 드라이버 개발자가 제공 됩니다.  
  
 프로그램은 ODBC 구성 요소를 개별 설치할 수도 있습니다. 드라이버 관리자를 설치 하려면 프로그램이 먼저 호출 하는 `SQLInstallDriverManager` installer DLL 드라이버 관리자에 대 한 대상 디렉터리를 가져올 수 있습니다. 이 일반적으로 Windows Dll이 상주 하는 디렉터리입니다. 그런 다음 프로그램 ODBC의 [ODBC 드라이버 관리자] 섹션에는 정보를 사용합니다. 설치 디스크에서이 디렉터리에 드라이버 관리자 및 관련된 파일을 복사 하려면 INF 파일입니다. 개별 드라이버를 설치 하려면 프로그램이 먼저 호출 하는 `SQLInstallDriver` 드라이버 사양에서 ODBCINST에 추가 하려면 DLL이 설치 관리자에서 합니다. INI 파일 (또는 nt 레지스트리). `SQLInstallDriver` 드라이버의 대상 디렉터리를 반환 합니다.-일반적으로 Windows Dll이 상주 하는 디렉터리입니다. 프로그램에서 odbc 드라이버의 섹션에는 정보를 사용 하 여 합니다. 설치 디스크에서이 디렉터리에 드라이버 DLL 및 관련된 파일을 복사 하려면 INF 파일입니다.  
  
 대 한 자세한 내용은 ODBC 합니다. INF, ODBCINST 합니다. INI와 설치 관리자 API를 사용 하 여 ODBC SDK를 참조 하십시오. *Programmer's Reference* 19 장, ODBC 소프트웨어를 설치 합니다.  
  
##  <a name="_mfcnotes_writing_an_odbc_administrator"></a> ODBC 관리자를 작성합니다.  
 MFC 데이터베이스 응용 프로그램을 설정 하 고 다음과 같이 두 가지 방법 중 하나에서 ODBC 데이터 소스를 구성할 수 있습니다.  
  
-   ODBC 관리자 (또는 제어판 항목을 프로그램으로 사용 가능)를 사용 합니다.  
  
-   데이터 원본을 구성 하는 고유의 프로그램을 만듭니다.  
  
 데이터 소스를 구성 하는 프로그램에서는 설치 관리자로 DLL 함수 호출 합니다. DLL 설치 관리자 설치 데이터 원본을 구성 하는 DLL을 호출 합니다. 각 드라이버;에 대해 하나의 설치 프로그램 DLL은 드라이버 자체 DLL 또는 별도 DLL 수도 있습니다. 설치 DLL 메시지 사용자에 게는 드라이버가 지원 되는 경우 데이터 원본 및 기본 변환기에 연결 하는 데 필요한 정보를 표시 합니다. 그런 다음 DLL 및 Windows Api는 ODBC에서이 정보를 기록 하는 설치 관리자를 호출 합니다. INI 파일 (또는 레지스트리)입니다.  
  
 프로그램이 호출 된 사용자 수를 추가, 수정 및 데이터 원본을 삭제 대화 상자를 표시 하려면 `SQLManageDataSources` DLL 설치 관리자에서 합니다. 이 함수는 설치 관리자는 제어판에서 DLL을 호출 될 때 호출 됩니다. 추가, 수정 또는 데이터 원본을 삭제 하려면 `SQLManageDataSources` 호출 `ConfigDSN` 해당 데이터 원본과 관련 된 드라이버 설치 DLL에서에서 합니다. 원본 데이터를 직접 추가, 수정 또는 삭제, 프로그램이 호출 하는 `SQLConfigDataSource` DLL 설치 관리자에서 합니다. 데이터 원본 및 수행할 동작을 지정 하는 옵션의 이름을 전달 하는 프로그램입니다. `SQLConfigDataSource` 호출 `ConfigDSN` DLL 설치 프로그램에서 인수를 전달 하 고 `SQLConfigDataSource`합니다.  
  
 자세한 내용은 ODBC SDK를 참조 하십시오. *Programmer's Reference* 23 장, 설치 DLL 함수 참조 및 24 장 Installer DLL 함수 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

