---
title: "데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SQLConfigDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC 데이터 소스 구성"
  - "ODBC 연결, 구성"
  - "ODBC 데이터 소스, 구성"
  - "SQLConfigDataSource 메서드 예제"
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 ODBC\(Open Database Connectivity\) 데이터 소스 이름을 프로그래밍 방식으로 구성하는 방법에 대해 설명합니다.  이렇게 하면 사용자가 ODBC 관리자나 다른 프로그램을 사용하여 명시적으로 데이터 소스 이름을 지정하지 않아도 데이터에 액세스할 수 있습니다.  
  
 일반적으로 연결된 DBMS\(데이터베이스 관리 시스템\)에서 지원하는 경우 사용자가 ODBC 관리자를 실행하여 데이터 소스를 만들 수 있습니다.  
  
 ODBC 관리자를 사용하여 Microsoft Access ODBC 데이터 소스를 만드는 경우 기존의 .mdb 파일을 선택하거나 새 .mdb 파일을 만들 수 있습니다.  그러나 MFC ODBC 응용 프로그램에서 프로그래밍 방식으로 .mdb 파일을 만들 수는 없습니다.  따라서 Microsoft Access 데이터 소스\(.mdb 파일\)에 데이터를 넣어야 하는 응용 프로그램인 경우에는 빈 .mdb 파일을 만들고 필요할 때 사용하거나 복사해야 합니다.  
  
 그러나 프로그래밍 방식으로 데이터 소스를 만들 수 있는 DBMS도 많습니다.  일부 데이터 소스는 데이터베이스에 대한 디렉터리 사양을 유지 관리합니다.  즉, 디렉터리는 데이터 소스가 되고 데이터 소스 내의 각 테이블은 개별 파일\(dBASE의 경우 .dbf 파일\)에 저장됩니다.  Microsoft Access나 SQL Server 같은 다른 ODBC 데이터베이스용 드라이버를 사용할 때는 몇 가지 특정 기준을 갖추어야 데이터 소스를 설정할 수 있습니다.  예를 들어 SQL Server ODBC 드라이버를 사용할 때는 먼저 SQL Server 컴퓨터를 설정해야 합니다.  
  
##  <a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource 예제  
 다음 예제에서는 **::SQLConfigDataSource** ODBC API 함수를 사용하여 New Excel Data Source라는 새 Excel 데이터 소스를 만듭니다.  
  
```  
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",   
                   "DSN=New Excel Data Source\0"   
                   "Description=New Excel Data Source\0"   
                   "FileType=Excel\0"   
                   "DataDirectory=C:\\EXCELDIR\0"   
                   "MaxScanRows=20\0");  
```  
  
 데이터 소스는 실제로 디렉터리\(C:\\EXCELDIR\)이므로 이 디렉터리가 있어야 합니다.  Excel 드라이버는 디렉터리를 데이터 소스로, 파일을 개별 테이블로\(.xls 파일 당 테이블 한 개\) 사용합니다.  
  
 테이블 작성에 대한 자세한 내용은 [데이터 소스: ODBC 데이터 소스에서 프로그래밍 방식으로 테이블 작성](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)을 참조하십시오.  
  
 아래에서는 **::SQLConfigDataSource** ODBC API 함수에 전달해야 하는 매개 변수에 대해 설명합니다.  **::SQLConfigDataSource**를 사용하려면 Odbcinst.h 헤더 파일을 포함하고 Odbcinst.lib 가져오기 라이브러리를 사용해야 합니다.  또한 런타임에 Odbccp32.dll\(16비트인 경우 Odbcinst.dll\)이 경로에 있어야 합니다.  
  
 ODBC 관리자 또는 유사한 유틸리티를 사용하여 ODBC 데이터 소스 이름을 생성할 수 있습니다.  그러나 때로는 사용자가 별도의 유틸리티를 실행할 필요 없이 응용 프로그램에서 직접 데이터 소스 이름을 생성하여 액세스하는 것이 나을 수도 있습니다.  
  
 대개 제어판에 설치되는 ODBC 관리자를 통해 Windows 레지스트리\(16비트인 경우 Odbc.ini 파일\)에 항목을 추가하여 새 데이터 소스를 만듭니다.  ODBC 드라이버 관리자는 이 파일을 쿼리하여 데이터 소스에 대한 필요한 정보를 얻습니다.  **SQLConfigDataSource** 호출에 정보를 제공해야 하므로 레지스트리에 어떤 정보를 추가해야 하는지 알아야 합니다.  
  
 **::SQLConfigDataSource**를 사용하지 않고 응용 프로그램에서 직접 이러한 정보를 레지스트리에 추가할 수도 있지만 이러한 경우에도 해당 응용 프로그램은 드라이버 관리자가 데이터를 관리하는 데 사용하는 기술을 기반으로 해야 합니다.  따라서 최신 ODBC 드라이버 관리자가 데이터 소스에 대한 기록 유지를 다른 방법으로 구현하면 이 기술을 사용하는 모든 응용 프로그램은 작동하지 않게 됩니다.  API 함수가 제공되는 경우에는 대개 해당 함수를 사용하는 것이 좋습니다.  예를 들어, **::SQLConfigDataSource** 함수는 Odbc.ini 파일이나 레지스트리에 정보를 올바르게 작성하므로 이 함수를 사용하면 코드를 16비트에서 32비트로 이식할 수 있습니다.  
  
##  <a name="_core_sqlconfigdatasource_parameters"></a> SQLConfigDataSource 매개 변수  
 아래에서는 **::SQLConfigDataSource** 함수의 매개 변수에 대해 설명합니다.  이 내용의 대부분은 Visual C\+\+ 1.5 이상에 제공되는 ODBC API 프로그래머 참조에서 가져온 것입니다.  
  
###  <a name="_core_function_prototype"></a> 함수 프로토타입  
  
```  
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);  
```  
  
### 설명  
  
####  <a name="_core_parameters_and_usage"></a> 매개 변수와 사용법  
 *hwndParent*  
 ODBC 드라이버 관리자나 특정 ODBC 드라이버에서 사용자로부터 새 데이터 소스에 대해 추가 정보를 얻기 위해 만드는 대화 상자의 부모 창으로 지정되는 창입니다.  `lpszAttributes` 매개 변수에 충분한 정보를 제공하지 않으면 대화 상자가 나타납니다.  *hwndParent* 매개 변수는 **NULL**이 될 수 있습니다.  
  
 `lpszDriver`  
 드라이버 설명입니다.  이 설명은 실제 드라이버 이름\(DLL\)이 아니라 사용자에게 표시되는 이름입니다.  
  
 `lpszAttributes`  
 "keyname\=value" 형식의 속성 목록입니다.  목록에서 각 문자열은 null 종결자로 구분되며 목록 끝에는 두 개의 null 종결자가 있습니다.  이러한 특성은 주로 특정한 기본 드라이버의 기본 항목으로 새 데이터 소스를 위해 레지스트리에 기록됩니다.  이 함수와 관련하여 ODBC API 참조에는 나오지 않는 중요한 키로 새 데이터 소스의 이름을 지정하는 "DSN\(데이터 소스 이름\)" 키가 있습니다.  나머지 항목은 새 데이터 소스를 위한 드라이버에 대한 것입니다.  드라이버에서 사용자에게 대화 상자를 표시하여 새 값을 얻을 수 있으므로 항목을 모두 제공할 필요가 없는 경우도 많습니다. *hwndParent*를 **NULL**로 설정하면 됩니다. 새 값을 얻기 위한 대화 상자가 나타나지 않도록 명시적으로 기본값을 제공할 수도 있습니다.  
  
###### ODBC 관리자를 사용하여 lpszDriver 매개 변수에 대한 드라이버 설명을 확인하려면  
  
1.  ODBC 관리자를 실행합니다.  
  
2.  **추가**를 클릭합니다.  
  
 이렇게 하면 설치된 드라이버 및 설명이 나열됩니다.  이 설명을 `lpszDriver` 매개 변수로 사용합니다.  설명에 파일 확장명과 괄호가 있으면 이를 포함하여 "Excel Files \(\*.xls\)"처럼 전체 설명을 사용합니다.  
  
 다른 방법으로, 레지스트리\(16비트에서는 Odbcinst.ini 파일\)의 "ODBC Drivers" 키\(Odbcinst.ini에서는 \[ODBC Drivers\] 섹션\) 아래에서 모든 드라이버 항목과 설명을 검사할 수도 있습니다.  
  
 `lpszAttributes` 매개 변수의 키 이름과 값을 찾는 한 가지 방법은 Odbc.ini 파일을 검사하여 이미 구성된 데이터 소스를 찾는 것입니다. 이 경우 해당 데이터 소스는 ODBC 관리자에 의해 구성된 것일 수 있습니다.  
  
###### lpszAttributes 매개 변수에 대한 키 이름과 값을 찾으려면  
  
1.  Windows 레지스트리 편집기를 실행합니다\(16비트인 경우 Odbc.ini 파일을 엽니다\).  
  
2.  다음 방법 중 하나를 사용하여 ODBC 데이터 소스 정보를 찾습니다.  
  
    -   32비트인 경우 왼쪽 창에서 **HKEY\_CURRENT\_USER\\Software\\ODBC\\ODBC.INI\\ODBC Data Sources** 키를 찾습니다.  
  
         오른쪽 창에 "pub: REG\_SZ:*\<data source name\>*" 형식으로 항목이 나열됩니다. 여기서 *\<data source name\>*은 사용하려는 드라이버에 대해 원하는 설정으로 이미 구성되어 있는 데이터 소스입니다.  원하는 데이터 소스\(예: SQL Server\)를 선택합니다.  "pub:" 문자열 다음의 항목은 순서대로 `lpszAttributes` 매개 변수에서 사용하는 키 이름과 값입니다.  
  
    -   16비트의 경우 Odbc.ini 파일에서 \[*\<데이터 소스 이름\>*\]으로 표시된 섹션을 찾습니다.  
  
         이 줄 다음에는 "keyname\=value" 형식의 줄이 있습니다.  이러한 항목이 `lpszAttributes` 매개 변수에서 사용할 항목입니다.  
  
 사용하려는 특정 드라이버에 대한 설명서를 참조할 수도 있습니다.  드라이버에 대한 온라인 도움말에서 유용한 정보를 찾을 수 있으며 ODBC 관리자를 실행하여 도움말에 액세스할 수 있습니다.  이들 도움말 파일은 대개 Windows NT, Windows 3.1 및 Windows 95 모두에서 WINDOWS\\SYSTEM 디렉터리에 있습니다.  
  
###### ODBC 드라이버에 대한 온라인 도움말을 보려면  
  
1.  ODBC 관리자를 실행합니다.  
  
2.  **추가**를 클릭합니다.  
  
3.  드라이버 이름을 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
 ODBC 관리자에서 해당 드라이버에 대한 새 데이터 소스 만들기에 대한 정보가 나타났을 때 **도움말**을 클릭합니다.  그러면 해당 드라이버에 대한 도움말 파일이 열리고 이 파일에는 대개 드라이버 사용에 대한 중요한 정보가 들어 있습니다.  
  
## 참고 항목  
 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md)