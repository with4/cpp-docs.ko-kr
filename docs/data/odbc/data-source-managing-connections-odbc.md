---
title: "데이터 소스: 연결 관리(ODBC) | Microsoft Docs"
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
  - "연결 문자열[C++], 일반화"
  - "연결[C++], 데이터 소스"
  - "데이터 소스[C++], 연결"
  - "데이터베이스 연결[C++], 만들기"
  - "데이터베이스 연결[C++], MFC ODBC 클래스"
  - "데이터베이스[C++], 연결"
  - "데이터 소스 연결 끊기"
  - "연결 문자열의 일반화"
  - "GetDefaultConnect 메서드"
  - "ODBC[C++], 데이터 소스 연결 끊기"
  - "ODBC 연결[C++], 구성"
  - "ODBC 연결[C++], 데이터 소스에 연결"
  - "ODBC 연결[C++], 연결 끊기"
  - "ODBC 데이터 소스[C++], 연결"
  - "ODBC 데이터 소스[C++], 다중 사용자 환경"
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 소스: 연결 관리(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [데이터 소스 구성 방법](#_core_configuring_a_data_source).  
  
-   [다중 사용자 환경이 데이터 소스와 그 레코드 집합에 영향을 끼치는 방법](#_core_working_in_a_multiuser_environment).  
  
-   [데이터 소스의 연결 문자열을 일반화하는 이유](#_core_generalizing_the_connection_string).  
  
-   [데이터 소스에 연결하는 방법](#_core_connecting_to_a_specific_data_source).  
  
-   [데이터 소스의 연결을 끊는 방법](#_core_disconnecting_from_a_data_source).  
  
-   [CDatabase 개체를 다시 사용하는 방법](#_core_reusing_a_cdatabase_object).  
  
 데이터 소스에 연결하는 것은 데이터에 액세스하기 위해 DBMS와 통신을 설정하는 것을 의미합니다.  응용 프로그램에서 ODBC 드라이버를 통해 데이터 소스에 연결하면 드라이버가 로컬에서 또는 네트워크를 통해 연결을 설정합니다.  
  
 해당 ODBC 드라이버가 있으면 어떤 데이터 소스에나 연결할 수 있습니다.  응용 프로그램 사용자도 해당 데이터 소스에 대한 ODBC 드라이버를 가지고 있어야 합니다.  ODBC 드라이버 재배포에 대한 자세한 내용은 [고객에게 ODBC 구성 요소 재배포](../../data/odbc/redistributing-odbc-components-to-your-customers.md)를 참조하십시오.  
  
##  <a name="_core_configuring_a_data_source"></a> 데이터 소스 구성  
 ODBC 관리자를 사용하여 데이터 소스를 구성합니다.  설치 후에도 ODBC 관리자를 사용하여 데이터 소스를 추가하거나 제거할 수 있습니다.  응용 프로그램을 만들 때는 사용자에게 ODBC 관리자를 사용하여 데이터 소스를 추가하도록 하거나 ODBC 설치를 직접 호출하도록 응용 프로그램에 이 기능을 포함할 수도 있습니다.  자세한 내용은 [ODBC 관리자](../../data/odbc/odbc-administrator.md)를 참조하십시오.  
  
 Excel 파일을 데이터 소스로 사용할 수 있으며 이 경우 파일이 등록되어 **데이터 소스 선택** 대화 상자에 나타나도록 구성해야 합니다.  
  
#### Excel 파일을 데이터 소스로 사용하려면  
  
1.  ODBC 데이터 소스 관리자를 사용하여 파일을 구성합니다.  
  
2.  **파일 DSN** 탭에서 **추가**를 클릭합니다.  
  
3.  **새 데이터 소스 만들기** 대화 상자에서 Excel 드라이버를 선택하고 **다음**을 클릭합니다.  
  
4.  **찾아보기**를 클릭하고 데이터 소스로 사용할 파일 이름을 선택합니다.  
  
> [!NOTE]
>  .xls 파일을 보려면 드롭다운 메뉴에서 **모든 파일**을 선택해야 합니다.  
  
1.  **다음**, **마침**을 차례로 클릭합니다.  
  
2.  **ODBC Microsoft Excel 설정** 대화 상자에서 데이터베이스 버전 및 통합 문서를 선택합니다.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> 다중 사용자 환경에서의 작업  
 데이터 소스에 여러 사용자가 연결되어 있으면 레코드 집합의 데이터를 조작하는 중에 다른 사용자가 데이터를 변경할 수 있습니다.  마찬가지로 사용자가 변경하는 내용이 다른 사용자의 레코드 집합에 영향을 줍니다.  자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 및 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)을 참조하십시오.  
  
##  <a name="_core_generalizing_the_connection_string"></a> 연결 문자열의 일반화  
 마법사는 기본 연결 문자열을 사용하여 데이터 소스로 연결을 설정합니다.  응용 프로그램을 개발하는 동안 이 연결을 사용하여 테이블과 열을 볼 수 있습니다.  그러나 이 기본 연결 문자열은 응용 프로그램을 통해 사용자가 데이터 소스에 연결하는 데 적합하지 않을 수도 있습니다.  예를 들어 사용자의 데이터 소스 및 그 위치에 대한 경로가 응용 프로그램 개발 동안 사용한 것과 다를 수 있습니다.  이 경우 [CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md) 멤버 함수를 좀 더 일반적인 방법으로 다시 구현하고 마법사에서 구현된 것은 삭제해야 합니다.  예를 들어, 아래와 같은 방법을 사용합니다.  
  
-   ODBC 관리자를 사용하여 연결 문자열을 등록하고 관리합니다.  
  
-   연결 문자열을 편집하여 데이터 소스 이름을 제거합니다.  프레임워크는 ODBC를 데이터 소스로 제공하며 ODBC는 런타임에 데이터 소스 이름 및 필요한 다른 연결 정보를 요구하는 대화 상자를 표시합니다.  
  
-   데이터 소스 이름만을 제공합니다.  필요한 경우 ODBC에서 사용자 ID와 암호를 요구합니다.  예를 들어 일반화하기 전의 연결 문자열은 아래와 같습니다.  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     이 연결 문자열은 Windows NT 통합 보안을 사용하는 트러스트 연결을 지정합니다.  심각한 보안 문제가 발생하므로 하드 코딩한 암호나 빈 암호를 사용하면 안 됩니다.  그 대신 `GetDefaultConnect`에 새 연결 문자열을 사용하여 사용자 ID와 암호를 쿼리하도록 합니다.  
  
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
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> 특정 데이터 소스에 연결  
 특정 데이터 소스에 연결하려면 [ODBC 관리자](../../data/odbc/odbc-administrator.md)를 사용하여 해당 데이터 소스가 이미 구성되어 있어야 합니다.  
  
#### 특정 데이터 소스에 연결하려면  
  
1.  `CDatabase` 개체를 생성합니다.  
  
2.  해당 개체의 `OpenEx` 또는 **Open** 멤버 함수를 호출합니다.  
  
 마법사로 지정한 데이터 소스와는 다른 데이터 소스를 지정하는 방법에 대한 정보는 MFC 참조의 [CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md) 또는 [CDatabase::Open](../Topic/CDatabase::Open.md)을 참조하십시오.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> 데이터 소스 연결 끊기  
 `CDatabase`의 **Close** 멤버 함수를 호출하기 전에 열려 있는 모든 레코드 집합을 닫아야 합니다.  `CDatabase` 개체와 연결되어 있는 레코드 집합을 닫으면 보류 중인 모든 `AddNew` 또는 **Edit** 문이 취소되고 보류 중인 모든 트랜잭션이 롤백됩니다.  
  
#### 데이터 소스의 연결을 끊으려면  
  
1.  `CDatabase` 개체의 [Close](../Topic/CDatabase::Close.md) 멤버 함수를 호출합니다.  
  
2.  다시 사용하지 않으려면 개체를 삭제합니다.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> CDatabase 개체 다시 사용  
 연결을 끊은 후 `CDatabase` 개체를 다시 사용할 수 있습니다. 이 개체를 사용하여 같은 데이터 소스 또는 다른 데이터 소스에 연결할 수 있습니다.  
  
#### CDatabase 개체를 다시 사용하려면  
  
1.  개체의 원래 연결을 닫습니다.  
  
2.  개체를 삭제하지 말고 `OpenEx` 또는 **Open** 멤버 함수를 다시 호출합니다.  
  
## 참고 항목  
 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md)   
 [데이터 소스: 데이터 소스의 스키마 확인\(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)