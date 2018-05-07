---
title: '데이터 소스: 연결 관리 (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 100c06773a8f0ffa79631339384bd4ec42fa4b52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-managing-connections-odbc"></a>데이터 소스: 연결 관리(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에 설명 합니다.  
  
-   [데이터 소스를 구성 하는 방법](#_core_configuring_a_data_source)합니다.  
  
-   [데이터 원본 및 그 레코드 집합 다중 사용자 환경에 미치는](#_core_working_in_a_multiuser_environment)합니다.  
  
-   [데이터 원본에 연결 문자열을 일반화 하는 이유](#_core_generalizing_the_connection_string)합니다.  
  
-   [데이터 원본에 연결 하는 방법](#_core_connecting_to_a_specific_data_source)합니다.  
  
-   [데이터 원본에서 연결 해제](#_core_disconnecting_from_a_data_source)합니다.  
  
-   [CDatabase 개체 다시 사용 하는 방법](#_core_reusing_a_cdatabase_object)합니다.  
  
 데이터 원본에 연결할 데이터에 액세스 하기 위해 DBMS와 통신을 설정 하는 것을 의미 합니다. ODBC 드라이버를 통해 응용 프로그램에서 데이터 원본에 연결 하면 로컬 또는 네트워크를 통해 드라이버,에 대 한 연결을 만듭니다.  
  
 ODBC 드라이버는 권한이 있는 모든 데이터 소스에 연결할 수 있습니다. 응용 프로그램의 사용자는 해당 데이터 원본에 대 한 ODBC 드라이버가 있어야 합니다. ODBC 드라이버 재배포 하는 방법에 대 한 자세한 내용은 참조 [고객에 게 ODBC 구성 요소 재배포](../../data/odbc/redistributing-odbc-components-to-your-customers.md)합니다.  
  
##  <a name="_core_configuring_a_data_source"></a> 데이터 소스 구성  
 ODBC 관리자는 데이터 원본을 구성 하는 데 사용 됩니다. 데이터 원본이 추가 또는 제거 하려면 설치 후 ODBC 관리자를 사용할 수 있습니다. 응용 프로그램을 만들 때 전달할 수 있습니다. 하거나 ODBC 관리자를 데이터 소스를 추가 하도록 알리는 사용자 또는 직접 ODBC 설치 호출을 수행 하 여 응용 프로그램에이 기능을 빌드할 수 있습니다. 자세한 내용은 참조 [ODBC 관리자](../../data/odbc/odbc-administrator.md)합니다.  
  
 Excel 파일을 사용 하 여 데이터 원본으로 등록 하 고에 표시 되도록 파일을 구성 해야 하는 **데이터 원본 선택** 대화 상자.  
  
#### <a name="to-use-an-excel-file-as-a-data-source"></a>Excel 파일을 데이터 원본으로 사용 하려면  
  
1.  ODBC 데이터 원본 관리자와 파일을 구성 합니다.  
  
2.  에 **파일 DSN** 탭을 클릭 **추가**합니다.  
  
3.  에 **새 데이터 원본 만들기** 대화 상자에서 Excel 드라이버를 선택한 다음 **다음**합니다.  
  
4.  클릭 **찾아보기**를 데이터 소스로 사용 될 파일의 이름을 선택 합니다.  
  
> [!NOTE]
>  선택 해야 할 수도 **모든 파일** .xls 파일을 보려면 드롭다운 메뉴에 있습니다.  
  
1.  **다음**을 클릭한 다음 **마침**을 클릭합니다.  
  
2.  에 **ODBC Microsoft Excel 설치** 대화 상자에서 데이터베이스 버전 및 통합 문서를 선택 합니다.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> 다중 사용자 환경에서 작업  
 여러 사용자가 데이터 원본에 연결 된 경우에 레코드 집합에서 조작 하는 동안 데이터를 변경할 수 있습니다. 마찬가지로, 변경 내용을 다른 사용자의 영향을 줄 수 있습니다. 자세한 내용은 참조 [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 및 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="_core_generalizing_the_connection_string"></a> 연결 문자열의 일반화  
 마법사 기본 연결 문자열을 사용 하 여 데이터 원본에 대 한 연결을 설정 합니다. 이 연결을 사용 하 여 응용 프로그램을 개발 하는 동안 테이블 및 열을 볼 수 있습니다. 그러나이 기본 연결 문자열은 응용 프로그램을 통해 데이터 원본에 대 한 사용자의 연결에 대 한 적절 한 아닐 수 있습니다. 예를 들어의 데이터 소스 및 해당 위치의 경로를 응용 프로그램 개발에 사용 된 것과에서 다른 수 있습니다. 다시 구현 해야 경우에 [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) 멤버 보다 일반적인 방법으로 함수를 구현 마법사를 취소 합니다. 예를 들어, 다음 방법 중 하나를 사용 합니다.  
  
-   등록 하 고 ODBC 관리자를 사용 하 여 연결 문자열을 관리 합니다.  
  
-   연결 문자열을 편집 하 고 데이터 원본 이름을 제거 합니다. 프레임 워크 데이터 소스로; ODBC를 제공합니다. 런타임 시 ODBC에는 데이터 원본 이름 및 기타 필요한 연결 정보를 묻는 대화 상자가 표시 됩니다.  
  
-   데이터 원본 이름을 제공 합니다. ODBC는 필요한 경우 사용자 ID와 암호를 요청 합니다. 예를 들어, 일반화 하기 전에 연결 문자열은 다음과 같습니다.  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     이 연결 문자열에는 Windows NT 통합 보안을 사용 하는 신뢰할 수 있는 연결을 지정 합니다. 암호를 하드 코딩 하지 않아야 하거나 심각한 보안 문제가 만듭니다 있으므로 방법은 빈 암호를 지정 하 합니다. 대신, 제공할 수 있습니다 `GetDefaultConnect` 사용자 ID와 암호에 대 한 쿼리를 새 연결 문자열입니다.  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> 특정 데이터 원본에 연결  
 특정 데이터 원본에 연결할 데이터 원본에 이미 구성 되어 있어야 합니다와 [ODBC 관리자](../../data/odbc/odbc-administrator.md)합니다.  
  
#### <a name="to-connect-to-a-specific-data-source"></a>특정 데이터 원본에 연결 하려면  
  
1.  생성 된 `CDatabase` 개체입니다.  
  
2.  호출의 `OpenEx` 또는 **열려** 멤버 함수입니다.  
  
 마법사와 함께 지정 되어 있지 않은 것 이면 데이터 소스를 지정 하는 방법에 대 한 자세한 내용은 참조 [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) 에 *MFC 참조*합니다.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> 데이터 원본에서 연결 끊기  
 호출 하기 전에 모든 열려 있는 레코드 집합이 닫아야는 **닫습니다** 의 멤버 함수 `CDatabase`합니다. 관련 된 레코드 집합에는 `CDatabase` 보류 중인 종료 하려는 개체 `AddNew` 또는 **편집** 문이 취소 되 고 보류 중인 모든 트랜잭션이 롤백됩니다.  
  
#### <a name="to-disconnect-from-a-data-source"></a>데이터 원본에서 연결을 끊으려면  
  
1.  호출 된 `CDatabase` 개체의 [닫기](../../mfc/reference/cdatabase-class.md#close) 멤버 함수입니다.  
  
2.  다시 사용 하려는 경우가 아니면 개체를 삭제 합니다.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> CDatabase 개체를 다시 사용  
 다시 사용할 수는 `CDatabase` 연결이 끊어진 후, 동일한 데이터 소스에 다시 연결 하거나 다른 데이터 원본에 연결 하는 데 사용 하는 개체입니다.  
  
#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase 개체를 다시 사용 하려면  
  
1.  원래 개체의 연결을 닫습니다.  
  
2.  호출 하는 개체를 제거 하는 대신 해당 `OpenEx` 또는 **열려** 멤버 함수를 다시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md)   
 [데이터 소스: 데이터 소스 (ODBC)의 스키마 확인](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)