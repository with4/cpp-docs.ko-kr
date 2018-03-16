---
title: "데이터 소스: ODBC 데이터 소스를 프로그래밍 방식으로 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SQLConfigDataSource
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac5756452a8b1c2d5dbf2f27ac7d3e1a8b069ca2
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성
이 항목에서는 프로그래밍 방식으로 데이터 원본 이름은 ODBC Open Database Connectivity ()를 구성 하는 방법에 대해 설명 합니다. 이 방법을 사용 하면 데이터 액세스를 명시적으로 데이터 원본의 이름을 지정 하려면 ODBC 관리자 또는 다른 프로그램을 사용 하도록 사용자를 강요 하지 않고도.  
  
 일반적으로 사용자가 연결된 된 데이터베이스 관리 시스템 (DBMS)이이 작업을 지 원하는 경우 데이터 원본을 만들려면 ODBC 관리자를 실행 합니다.  
  
 ODBC 관리자를 통해 Microsoft Access ODBC 데이터 소스를 만들 때 두 가지 선택 사항을 제공 됩니다: 기존.mdb 파일 선택 하거나 새.mdb 파일을 만들 수 있습니다. MFC ODBC 응용 프로그램에서.mdb 파일을 만드는 프로그래밍 방식은 없습니다. 따라서 응용 프로그램을 Microsoft Access 데이터 소스 (.mdb 파일)에 데이터를 배치 하 고 필요한 경우 것이 좋습니다 필요할 때마다 복사 하거나 사용할 수 있는 빈.mdb 파일을 보유 합니다.  
  
 그러나 여러 Dbms에는 프로그래밍 방식으로 데이터 소스를 만들을 수 있습니다. 일부 데이터 원본에는 데이터베이스에 대 한 디렉터리 사양을 유지 관리 합니다. 즉, 디렉터리는 데이터 원본 및 데이터 원본 내에서 각 테이블은 별도 파일에 저장 됩니다 (dBASE의 경우 각 테이블은.dbf 파일). Microsoft Access 및 SQL Server와 같은 다른 ODBC 데이터베이스에 대 한 드라이버 해야 데이터 원본 설정 먼저 특정 기준을 충족 되어야 합니다. 예를 들어 SQL Server ODBC 드라이버를 사용 하는 경우 SQL Server 컴퓨터를 설정 해야 합니다.  
  
##  <a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource 예제  
 다음 예제에서는 **:: SQLConfigDataSource** ODBC API 함수를 만드는 새 Excel 데이터 원본 이라는 새로운 Excel 데이터 원본:  
  
```  
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",   
                   "DSN=New Excel Data Source\0"   
                   "Description=New Excel Data Source\0"   
                   "FileType=Excel\0"   
                   "DataDirectory=C:\\EXCELDIR\0"   
                   "MaxScanRows=20\0");  
```  
  
 데이터 소스는 실제 디렉터리 (C:\EXCELDIR); 이 디렉터리가 있어야 합니다. Excel 드라이버는 디렉터리를 해당 데이터 원본 및 파일 (.xls 파일 마다 하나의 테이블) 개별 테이블 사용 합니다.  
  
 테이블을 만드는 방법에 대 한 자세한 내용은 참조 [데이터 소스: 프로그래밍 방식으로 ODBC 데이터 원본에 테이블을 만드는](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)합니다.  
  
 다음 정보를 전달 해야 하는 매개 변수 설명는 **:: SQLConfigDataSource** ODBC API 함수입니다. 사용 하도록 **:: SQLConfigDataSource**, Odbcinst.h 헤더 파일을 포함 하 고 Odbcinst.lib 가져오기 라이브러리를 사용 해야 합니다. 또한 Odbccp32.dll는 런타임에 (또는 Odbcinst.dll 16 비트)의 경로에 있어야 합니다.  
  
 ODBC 관리자 또는 이와 유사한 유틸리티를 사용 하 여 ODBC 데이터 원본 이름을 만들 수 있습니다. 그러나이 적합 한 경우가 액세스할 별도 유틸리티를 실행 하려면 사용자를 요구 하지 않고 응용 프로그램에서 직접 데이터 원본 이름을 만들 수 있습니다.  
  
 ODBC 관리자 (일반적으로 제어판에 설치)는 Windows 레지스트리에 (또는 Odbc.ini 파일에 16 비트) 항목을 배치 하 여 새 데이터 원본을 만듭니다. ODBC 드라이버 관리자는이 파일을 데이터 원본에 대 한 필요한 정보를 쿼리 합니다. 에 대 한 호출을 제공 해야 하기 때문에 레지스트리에 배치 해야 할 정보를 파악 해야 **:: SQLConfigDataSource**합니다.  
  
 이 정보를 사용 하지 않고 레지스트리에 직접 쓸 수 있지만 **:: SQLConfigDataSource**,이 작업을 수행 하는 응용 프로그램은 드라이버 관리자가 사용 하 여 데이터를 관리 하는 기술을에 의존 하므로 합니다. 최신 기록을 다른 방식으로 데이터 원본에 대 한 유지 ODBC 드라이버 관리자 구현 하면이 기법을 사용 하는 모든 응용 프로그램은 중단 합니다. 일반적으로 제공 되는 경우 API 함수를 사용 하는 것이 좋습니다. 예를 들어, 코드를 사용 하는 경우 32 비트에서 16 비트 이식할는 **:: SQLConfigDataSource** 함수 Odbc.ini 파일 또는 레지스트리를 올바르게 작성 때문에 작동 합니다.  
  
##  <a name="_core_sqlconfigdatasource_parameters"></a> SQLConfigDataSource 매개 변수  
 다음 설명의 매개 변수는 **:: SQLConfigDataSource** 함수입니다. ODBC API에서 대부분의 정보를 가져옵니다 *Programmer's Reference* Visual c + + 1.5 이상 버전에서 제공 합니다.  
  
###  <a name="_core_function_prototype"></a> 함수 프로토타입  
  
```  
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);  
```  
  
### <a name="remarks"></a>설명  
  
####  <a name="_core_parameters_and_usage"></a> 매개 변수 및 사용법  
 *hwndParent*  
 ODBC 드라이버 관리자 또는 특정 ODBC 드라이버를 새 데이터 원본에 대 한 사용자에 게 서 추가 정보를 얻기 위해 만드는 모든 대화 상자의 소유자로 지정 하는 창입니다. 경우는 `lpszAttributes` 매개 변수가 충분 한 정보를 제공 하지 않는, 대화 상자가 나타납니다. *창은* 매개 변수 수 **NULL**합니다.  
  
 `lpszDriver`  
 드라이버에 대 한 설명입니다. 실제 드라이버 이름 (DLL)가 아닌 사용자에 게 표시 이름입니다.  
  
 `lpszAttributes`  
 형식에서 특성의 목록 "keyname = value"입니다. 이러한 문자열은 두 개의 null 종결자 목록의 끝에 null 종결자로 구분 됩니다. 이러한 특성은 기본적으로 기본 드라이버 관련 항목을 새 데이터 원본에 대 한 레지스트리로 이동 합니다. 이 함수에 대 한 ODBC API 참조에 언급 하지 않은 중요 한 한 개의 키 "" ("데이터 원본 이름")을 지정 하는 DSN 새 데이터 원본의 이름입니다. 나머지 항목은 새 데이터 원본에 대 한 드라이버 관련이 있습니다. 종종 드라이버는 새 값에 대 한 대화 상자를 사용 하 여 사용자를 표시할 수 있습니다 때문에 모든 항목을 제공 하는 필요는 없습니다. (설정 *창은* 를 **NULL** 이 발생할 수 있습니다.) 명시적으로 기본값을 제공 하는 메시지가 표시 되지 않도록 할 수 있습니다.  
  
###### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC 관리자를 사용 하 여 lpszDriver 매개 변수에 대 한 드라이버에 대 한 설명을 확인 하려면  
  
1.  ODBC 관리자를 실행 합니다.  
  
2.  **추가**를 클릭합니다.  
  
 설치 된 드라이버와 해당 설명의 목록을 제공 합니다. 로이 설명을 사용 하 여는 `lpszDriver` 매개 변수입니다. Note 설명에 있는 경우 파일 이름 확장명 및 괄호를 포함 하 여 "Excel 파일 (*.xls)"과 같은 전체 설명을 사용 합니다.  
  
 대신, 레지스트리를 검사할 수 있습니다 (또는 16 비트 Odbcinst.ini 파일), 모든 드라이버 항목 및 "ODBC 드라이버" 레지스트리 키 아래 설명 (또는 Odbcinst.ini에서 [ODBC Drivers] 섹션) 목록이 포함 되어 있는 합니다.  
  
 키와 값을 찾을 수는 한 가지 방법은 `lpszAttributes` 매개 변수 (아마도 하나 ODBC 관리자가 구성 된)는 이미 구성 된 데이터 원본에 대 한 Odbc.ini 파일을 검사 하는 것입니다.  
  
###### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>LpszAttributes 매개 변수에 대 한 키와 값을 찾을 수  
  
1.  Windows 레지스트리 편집기를 실행 하거나, 16 비트 Odbc.ini 파일을 엽니다.  
  
2.  다음 중 하나를 사용 하 여 ODBC 데이터 소스 정보를 찾습니다.  
  
    -   32 비트에 대 한 키를 찾을 **HKEY_CURRENT_USER\Software\ODBC\ODBC 합니다. 데이터 원본 INI\ODBC** 왼쪽된 창에서.  
  
         오른쪽 창에는 형식의 항목 나열: "pub: REG_SZ:*<data source name>*" 여기서  *<data source name>*  은 하려는 드라이버에 대 한 원하는 설정으로 이미 구성 된 데이터 원본 사용 합니다. 예를 들어 SQL Server, 원하는 데이터 원본을 선택 합니다. 문자열 다음에 나오는 항목 "pub:"에서는 순서, 키 이름 및 값에서 사용 하 여 `lpszAttributes` 매개 변수입니다.  
  
    -   16 비트를 표시 하는 Odbc.ini 파일의 섹션을 찾습니다 [*\<데이터 원본 이름 >*].  
  
         폼의 다음이 줄이 줄은 "keyname = value"입니다. 이러한 항목이에서 사용 하 여 `lpszAttributes` 매개 변수입니다.  
  
 특정 드라이버를 사용 하는 것에 대 한 설명서를 참조할 수도 있습니다. ODBC 관리자를 실행 하 여 액세스할 수 있는 드라이버에 대 한 온라인 도움말의 유용한 정보를 찾을 수 있습니다. 이 도움말 파일은 일반적으로 Windows NT, Windows 3.1의 경우, 또는 Windows 95 WINDOWS\SYSTEM 디렉터리에 배치 됩니다.  
  
###### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC 드라이버에 대 한 온라인 도움말을 보려면  
  
1.  ODBC 관리자를 실행 합니다.  
  
2.  **추가**를 클릭합니다.  
  
3.  드라이버 이름을 선택 합니다.  
  
4.  **확인**을 클릭합니다.  
  
 해당 드라이버에 대 한 새 데이터 원본을 만들기 위한 정보를 표시 하는 ODBC 관리자 경우 클릭 **도움말**합니다. 일반적으로 드라이버의 사용에 관한 중요 한 정보를 포함 하는 해당 드라이버에 대 한 도움말 파일을 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)