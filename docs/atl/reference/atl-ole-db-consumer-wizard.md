---
title: "ATL OLE DB 소비자 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.consumer.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL OLE DB 소비자 마법사"
  - "ATL 프로젝트, ATL OLE DB 소비자 추가"
  - "연결 문자열[C++], OLE DB 소비자"
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL OLE DB 소비자 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 지정된 OLD DB 공급자를 통해 지정된 데이터 소스에 액세스하는 데 필요한 데이터 바인딩으로 OLE DB 소비자 클래스를 설정합니다.  
  
> [!NOTE]
>  `Class` 및 **.h 파일** 필드에 이름을 입력하기 전에 **데이터 소스** 단추를 클릭하여 데이터 소스를 선택해야 합니다.  
  
## UI 요소 목록  
 **데이터 소스**  
 **데이터 소스** 단추를 사용하면 지정된 OLD DB 공급자를 사용하여 지정된 데이터 소스를 설정할 수 있습니다.  이 단추를 클릭하면 **데이터 연결 속성** 대화 상자가 나타납니다.  연결 문자열 빌드 및 **데이터 연결 속성** 대화 상자에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] 설명서의 [데이터 연결 API 개요](https://msdn.microsoft.com/en-us/library/ms718102.aspx)를 참조하십시오.  
  
> [!NOTE]
>  이전 릴리스에서는 Shift 키를 누른 채 **데이터 소스** 단추를 클릭하면 파일 열기 대화 상자가 열려 .udl 파일을 선택할 수 있었습니다.  이 기능은 이제 지원되지 않습니다.  
  
 이 대화 상자에는 다음 네 가지 탭이 있습니다.  
  
-   **공급자** 탭  
  
-   **연결** 탭  
  
-   **고급** 탭  
  
-   **모두** 탭  
  
     다음 추가 정보는 **데이터 링크 속성** 대화 상자의 탭을 설명합니다.  
  
     마치려면 **확인**을 클릭합니다.  **데이터베이스 개체 선택** 대화 상자가 나타납니다.  이 대화 상자에서 소비자가 사용할 테이블, 뷰 또는 저장 프로시저를 선택합니다.  
  
     **공급자**  
     데이터 원본 연결을 관리하는 데 적절한 공급자를 선택합니다.  공급자 형식은 일반적으로 연결하고 있는 데이터베이스의 형식에 따라 결정됩니다.  `Next` 단추를 클릭하거나 **연결** 탭을 클릭합니다.  
  
     **Connection**  
     이 탭의 콘텐츠는 선택한 공급자에 따라 다릅니다.  여러 형식의 공급자가 있지만 이 구역은 두 가지 가장 일반적인 SQL 및 ODBC 데이터에 대한 연결을 다룹니다.  나머지는 여기에서 설명한 필드 상의 유사한 변형입니다.  
  
     SQL 데이터의 경우:  
  
    1.  **서버 이름 선택 또는 입력:** 드롭다운 목록 메뉴를 클릭하면 네트워크에 등록된 모든 데이터 서버가 표시되며 이 중 하나를 선택합니다.  
  
    2.  **서버 로그온 정보 입력:** 데이터 서버에 로그온하는 사용자 이름과 암호를 입력합니다.  
  
    3.  **서버에서 데이터베이스 선택:** 드롭다운 목록 메뉴를 클릭하면 데이터 서버에 등록된 모든 데이터베이스 서버가 표시되며 이 중 하나를 선택합니다.  
  
         또는  
  
         **데이터베이스 파일을 데이터베이스 이름으로 연결:** 데이터베이스로 사용할 파일을 지정합니다. 명시적 경로 이름을 입력합니다.  
  
        > [!NOTE]
        >  데이터 연결 속성 대화 상자의 "암호 저장 허용" 기능을 사용하면 보안 문제가 발생할 수 있습니다.  "서버 로그온 정보 입력"에는 다음과 같은 두 개의 라디오 단추가 있습니다.  
  
         **Windows NT의 통합 보안 사용**  
  
         **특정 사용자 이름 및 암호 사용**  
  
         **특정 사용자 이름 및 암호 사용**을 선택하면 "암호 저장 허용" 확인란을 사용하여 암호를 저장할 수 있지만 이 옵션은 안전하지 못합니다.  **Windows NT의 통합 보안 사용**을 선택하는 것이 좋습니다. 이 옵션은 암호가 암호화되기 때문에 안전합니다.  
  
         "암호 저장 허용"을 선택하려는 경우가 있을 수 있습니다. 예를 들어, 전용 데이터베이스 솔루션을 사용하여 라이브러리를 해제하는 경우 데이터베이스를 직접 액세스해서는 안 되고 중간 계층 응용 프로그램을 사용하여 선택한 인증 체계를 통해 사용자를 확인한 다음 사용자가 사용할 수 있는 데이터의 정렬을 제한합니다.  
  
         ODBC 데이터의 경우:  
  
         1.  **데이터 원본 지정:** 데이터 소스 이름 또는 연결 문자열을 사용할 수 있습니다.  
  
         **데이터 소스 이름 사용:** 이 드롭다운 목록은 시스템에 등록된 데이터 소스를 표시합니다.  [ODBC Data Source Administrator](!Alink("dasdkODBCDataSourceAdmin")).\-또는\-**연결 문자열 사용:**을 사용하여 사전에 데이터 소스를 설정할 수 있습니다. 이미 가져온 연결 문자열을 입력하거나, **빌드** 단추를 클릭하면 **데이터 원본 선택** 대화 상자를 표시합니다.  파일 또는 컴퓨터 데이터 원본을 선택하고 **확인**을 클릭합니다.  
  
        > [!NOTE]
        >  서버 탐색기에서 기존 연결의 속성을 확인하여 연결 문자열을 가져오거나 서버 탐색기에서 **연결 추가**를 두 번 클릭하여 연결을 만들 수 있습니다.  
  
         2.  **서버 로그온 정보 입력:** 데이터 서버에 로그온하는 사용자 이름과 암호를 입력합니다.  
  
         3.  사용할 초기 카탈로그를 입력합니다.  
  
         4.  **테스트 연결**을 클릭합니다. 테스트가 성공하면 **OK**를 클릭합니다.  그렇지 않을 경우 로그온 정보를 확인하고 다른 데이터베이스 또는 다른 데이터 서버를 시도해 보십시오.  
  
     **고급**  
     **네트워크 설정:** [Impersonation level](!Alink("_com_Impersonation_Levels"))\(클라이언트를 가장할 때 서버가 사용하는 것이 허용된 가장 수준으로 RPC 가장 수준에 직접 대응\) 및 **보호 수준**\(클라이언트와 서버 간에 전송되는 데이터의 보호 수준으로 RPC 보호 수준에 직접 대응\)을 지정합니다.  
  
     **기타: Connect timeout**에서 시간 초과가 발생 하기 전에 허용할 유휴 시간\(초\)을 지정합니다.  **액세스 권한**에서 데이터 연결에 액세스 권한을 지정합니다.  
  
     고급 초기화 속성에 대한 자세한 내용은 해당 OLE DB 공급자와 함께 제공되는 설명서를 참조하십시오.  
  
     **모두**  
     이 탭은 데이터 소스 및 사용자가 지정한 연결에 대한 초기화 속성의 요약을 표시합니다.  이러한 값은 편집할 수 있습니다.  
  
     마치려면 **확인**을 클릭합니다.  **데이터베이스 개체 선택** 대화 상자가 나타납니다.  이 대화 상자에서 소비자가 사용할 테이블, 뷰 또는 저장 프로시저를 선택합니다.  
  
 `Class`  
 데이터 소스를 선택하면 선택한 테이블 또는 저장 프로시저를 기반으로 하는 기본 클래스 이름이 이 상자에 입력됩니다. 아래의 **데이터 원본 선택**을 참조하십시오.  클래스 이름을 편집할 수 있습니다.  
  
 **.h 파일**  
 데이터 소스를 선택하면 선택한 테이블 또는 저장 프로시저를 기반으로 하는 기본 헤더 클래스 이름이 이 상자에 입력됩니다. 아래의 **데이터 원본 선택**을 참조하십시오.  헤더 파일의 이름을 편집하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **특성 사용**  
 이 옵션은 특성 또는 템플릿 선언 중 어느 것을 사용하여 소비자 클래스를 만들 것인지 지정합니다.  이 옵션을 선택하면 템플릿 선언 대신 특성이 사용됩니다. 기본값입니다.  이 옵션 선택을 취소하면 특성 대신 템플릿 선언이 사용됩니다.  
  
-   테이블의 소비자 **형식**을 선택하는 경우 마법사는 `db_source` 및 **db\_table** 특성을 사용하여 테이블 및 테이블 접근자 클래스 선언을 만들고 **db\_column**을 사용하여 열 맵을 만듭니다. 예를 들면 다음과 같습니다.  
  
    ```  
    // Inject table class and table accessor class declarations  
    [  
        db_source("<initialization_string>"),  
        db_table("dbo.Orders")  
    ]  
    ...  
    // Column map  
        [ db_column(1, status=m_dwOrderIDStatus,         length=m_dwOrderIDLength) ] LONG m_OrderID;  
        [ db_column(2, status=m_dwCustomerIDStatus,         length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
        ...  
    ```  
  
     마법사는 `CTable` 템플릿 클래스를 사용하여 테이블 및 테이블 접근자 클래스를 선언하고 BEGIN\_COLUMN\_MAP 및 END\_COLUMN\_MAP 매크로를 사용하여 열 맵을 만들지 않습니다. 예를 들면 다음과 같습니다.  
  
    ```  
    // Table accessor class  
    class COrdersAccessor;  
    // Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor> >;  
    ...  
    // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor)  
        COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID,         m_dwOrderIDLength, m_dwOrderIDStatus)  
        COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID,         m_dwCustomerIDLength, m_dwCustomerIDStatus)  
        ...  
    END_COLUMN_MAP()  
    ```  
  
-   명령의 소비자 **형식**을 선택하는 경우 마법사는 `db_source` 및 **db\_command** 특성을 사용하고 **db\_column**을 사용하여 열 맵을 만듭니다. 예를 들면 다음과 같습니다.  
  
    ```  
    [  
        db_source("<initialization_string>"),  
        db_command("SQL_command")  
    ]  
    ...  
    // Column map using db_column is the same as for consumer type of 'table'  
    ```  
  
     마법사는 명령 클래스의 .h 파일에서 명령 및 명령 접근자 클래스 선언을 사용하지 않습니다. 예를 들면 다음과 같습니다.  
  
    ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor> >;  
    ...  
    // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as  
    // for consumer type of 'table'  
    ```  
  
 자세한 내용은 [Basic Mechanics of Attributes](../../windows/basic-mechanics-of-attributes.md)를 참조하십시오.  
  
 **Type**  
 이 라디오 단추 중 하나를 선택하여 소비자 클래스가 `CTable` 또는 `CCommand`\(기본값\) 중 어디에서 파생될지를 지정합니다.  
  
 **표**  
 `CTable` 또는 **db\_table**을 사용하여 테이블과 테이블 접근자 클래스 선언을 만들려면 이 옵션을 선택합니다.  
  
 **명령**  
 `CCommand` 또는 **db\_command**를 사용하여 명령 및 명령 접근자 클래스 선언을 만들려면 이 옵션을 선택합니다.  이 옵션은 기본적으로 선택됩니다.  
  
 **지원**  
 소비자에서 지원하는 업데이트 종류를 지정하려면 이 확인란을 선택합니다. 기본적으로 아무 것도 선택되어 있지 않습니다.  다음 각 옵션은 [DBPROP\_IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715892.aspx)를 설정하고 속성 집합 맵에서 [DBPROP\_UPDATABILITY](https://msdn.microsoft.com/en-us/library/ms722676.aspx)에 대한 적절한 항목을 설정합니다.  
  
 **Change**  
 소비자가 행 집합에서 행 데이터 업데이트를 지원하도록 지정합니다.  
  
 **Insert**  
 소비자가 행 집합에 행 삽입을 지원하도록 지정합니다.  
  
 **Delete**  
 소비자가 행 집합에서 행 삭제를 지원하도록 지정합니다.  
  
## 참고 항목  
 [ATL OLE DB Consumer](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [연결 문자열 및 데이터 연결\(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms718376.aspx)