---
title: "ATL OLE DB 소비자 마법사 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- connection strings [C++], OLE DB consumers
- ATL OLE DB Consumer Wizard
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6e35ce9038a8fd8f7aeeb00139511a8f45c1257d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB 소비자 마법사
이 마법사를 설정 하는 OLE DB 소비자 클래스 데이터 바인딩을 사용 하 여 지정된 된 OLE DB 공급자를 통해 지정 된 데이터 원본에 액세스 하는 데 필요한 합니다.  
  
> [!NOTE]
>  이 마법사를 사용 하려면 클릭 하는 **데이터 소스** 단추에 이름을 입력 하기 전에 데이터 원본을 선택 하는 `Class` 및 **.h 파일** 필드입니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **데이터 원본**  
 **데이터 소스** 단추 지정된 된 OLE DB 공급자를 사용 하 여 지정 된 데이터 소스를 설정할 수 있습니다. 이 단추를 클릭할 때는 **데이터 연결 속성** 대화 상자가 나타납니다. 연결 문자열 작성에 대 한 자세한 내용은 및 **데이터 연결 속성** 대화 상자, 참조 [데이터 연결 API 개요](https://msdn.microsoft.com/library/ms718102.aspx) 에 [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)] 설명서입니다.  
  
> [!NOTE]
>  Shift 키를 클릭 하는 이전 릴리스에서 **데이터 원본** 단추는 파일 열기 대화 상자가 열려 데이터 연결 (.udl) 파일을 선택할 수 있습니다. 이 기능은 지원 되지 않습니다.  
  
 대화 상자에는 네 개의 탭에 있습니다.  
  
- **공급자** 탭  
  
- **연결** 탭  
  
- **고급** 탭  
  
- **모든** 탭  
  
     다음과 같은 추가 정보에는 탭에 설명 된 **데이터 연결 속성** 대화 상자입니다.  
  
     클릭 **확인** 완료 합니다. **데이터베이스 개체 선택** 대화 상자가 나타납니다. 이 대화 상자에서 테이블, 뷰 또는 소비자가 사용할 저장된 프로시저를 선택 합니다.  
  
 **공급자**  
     데이터 원본에 대 한 연결을 관리 하기 위한 적절 한 공급자를 선택 합니다. 형식의 공급자는 일반적으로 연결 중인 데이터베이스의 유형에 의해 결정 됩니다. 클릭 하 여 `Next` 단추를 클릭 하거나는 **연결** 탭 합니다.  
  
 **연결**  
     이 탭의 내용은 선택한 공급자에 따라 다릅니다. 이 섹션에서는 두 가지에 대 한 연결을 설명 다양 한 유형의 공급자에는 없지만 가장 일반적인: SQL 및 ODBC 데이터입니다. 다른 필드는 여기에서 설명 하는 필드에서 유사한 변형입니다.  
  
     SQL 데이터의 경우  
  
    1. **서버 이름 선택 또는 입력:** 네트워크의 모든 등록 된 데이터 서버를 표시 하려면 드롭다운 목록에서 메뉴를 클릭 하 고 하나를 선택 합니다.  
  
    2. **서버에 로그온 정보 입력:** 사용자 이름 및 데이터 서버에 로그온 할 암호를 입력 합니다.  
  
    3. **서버에서 데이터베이스를 선택 합니다.** 데이터 서버에 등록 된 모든 데이터베이스를 표시 하려면 드롭다운 목록에서 메뉴를 클릭 하 고 하나를 선택 합니다.  
  
         또는  
  
 **데이터베이스 이름으로 데이터베이스 파일 첨부:** 데이터베이스로 사용할 파일을 지정 합니다; 명시적 경로 이름을 입력 합니다.  
  
        > [!NOTE]
        >  There is a security problem with the "Allow saving of password" feature of the Data Link Properties dialog box. In "Enter information to log on to the server," there are two radio buttons:  
  
 **Windows NT 통합 보안을 사용 하 여**  
  
 **특정 사용자 이름 및 암호를 사용 하 여**  
  
         If you select **Use a specific user name and password**, you have the option of saving the password (using the check box for "Allow saving password"); however, this option is not secure. It is recommended that you select **Use Windows NT integrated security**; this option is secure because it encrypts the password.  
  
         There might be situations in which you want to select "Allow saving password." For example, if you are releasing a library with a private database solution, you should not access the database directly but instead use a middle-tier application to verify the user (through whatever authentication scheme you choose) and then limit the sort of data available to the user.  
  
         For ODBC data:  
  
         1. **Specify the source of data:** You can use a data source name or a connection string.  
  
 **데이터 원본 이름 사용:** 이 드롭다운 목록에서 컴퓨터에 등록 하는 데이터 소스가 표시 됩니다. ODBC 데이터 원본 관리자를 사용 하 여 미리 데이터 소스를 설정할 수 있습니다-또는-**연결 문자열을 사용 하 여:** 이미가지고 또는 클릭 하 여 연결 문자열을 입력 하거나는 **빌드** ; 단추는 **데이터 원본 선택** 대화 상자가 나타납니다. 파일 또는 컴퓨터 데이터 소스를 선택 하 고 클릭 **확인**합니다.  
  
        > [!NOTE]
        >  You can obtain a connection string by viewing the properties of an existing connection in Server Explorer, or you can create a connection by double-clicking **Add Connection** in Server Explorer.  
  
         2. **Enter information to log on to the server:** Enter a user name and password to log on to the data server.  
  
         3. Enter the initial catalog to use.  
  
         4. Click **Test Connection**; if the test succeeds, click **OK**. If not, check your logon information, try another database, or try another data server.  
  
 **고급**  
 **네트워크 설정:** 지정은 **가장 수준을** (서버에서 클라이언트를 가장할 때 사용할 수; RPC 가장 수준에 직접적으로 해당 하는 가장 수준) 및 **보호 수준을** (RPC 보호 수준에 직접 해당 데이터의 보호 수준을 클라이언트와 서버 간에 전송).  
  
 **기타:** 에서 **연결 제한 시간**, 시간 초과가 발생 하기 전에 허용 되는 유휴 시간을 초 수를 지정 합니다. **대 한 액세스 권한을**, 데이터 연결에 대 한 액세스 권한을 지정 합니다.  
  
     고급 초기화 속성에 대 한 자세한 내용은 각 특정 OLE DB 공급자와 함께 제공 되는 설명서를 참조 하십시오.  
  
 **All**  
     이 탭에는 데이터 소스와 사용자가 지정한 연결에 대 한 초기화 속성 요약이 표시 됩니다. 이러한 값을 편집할 수 있습니다.  
  
     클릭 **확인** 완료 합니다. **데이터베이스 개체 선택** 대화 상자가 나타납니다. 이 대화 상자에서 테이블, 뷰 또는 소비자가 사용할 저장된 프로시저를 선택 합니다.  
  
 `Class`  
 데이터 소스를 선택한 후이 상자는 테이블 또는 선택한 저장된 프로시저를 기반으로 하는 기본 클래스 이름이 채워집니다 (참조 **데이터 원본 선택** 아래). 클래스 이름을 편집할 수 있습니다.  
  
 **.h 파일**  
 데이터 소스를 선택한 후이 상자는 테이블 또는 선택한 저장된 프로시저를 기반으로 하는 기본 헤더 클래스 이름이 채워집니다 (참조 **데이터 원본 선택** 아래). 헤더 파일의 이름을 편집 하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **특성 사용**  
 이 옵션은 특성 또는 서식 파일 정의 사용 하 여 소비자 클래스를 만들 있는지 여부를 지정 합니다. 이 옵션을 선택 하면 마법사 (기본 옵션 임) 템플릿 선언 하는 대신 특성을 사용 합니다. 이 옵션의 선택을 취소 하면 특성 대신 템플릿 선언이 사용 합니다.  
  
-   소비자를 선택 하는 경우 **형식** 마법사 사용 하 여 테이블의는 `db_source` 및 **db_table** 특성을 테이블 및 테이블 접근자 클래스 선언 및 사용 하 여 **db_column** 예를 들어 열 맵을 만들려면:  
  
 ``` 
 // Inject table class and table accessor class declarations  
 [db_source("<initialization_string>"), db_table("dbo.Orders")]  
 ... 
 // Column map  
 [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;  
 [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
 ...  
 ```  
  
     사용 하는 대신는 `CTable` 테이블 및 테이블 접근자 클래스 및 예를 들어 열 맵을 만들려면 BEGIN_COLUMN_MAP 및 END_COLUMN_MAP 매크로 선언 하는 템플릿 클래스:  
  
 ``` 
 // Table accessor class  
    class COrdersAccessor; *// Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor>>;  
 ... 
 // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor) 
    COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)  
    COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)  
 ...  
    END_COLUMN_MAP() 
 ```  
  
-   소비자를 선택 하는 경우 **형식** 마법사 사용 하 여 명령에 `db_source` 및 **db_command** 특성 및 사용 하 여 **db_column** 예를 들어 열 맵을 만들려면:  
  
 ```  
 [db_source("<initialization_string>"), db_command("SQL_command")]  
 ... 
 // Column map using db_column is the same as for consumer type of 'table'  
 ```  
  
     명령 및 명령 접근자를 사용 하는 대신 클래스 선언을 명령 클래스의.h 파일의 예를 들어:  
  
 ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;  
 ... 
 // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
 // for consumer type of 'table'  
 ```  
  
 참조 [특성의 기본 메커니즘](../../windows/basic-mechanics-of-attributes.md) 에 대 한 자세한 내용은 합니다.  
  
 **Type**  
 소비자 클래스에서 파생 됩니다 있는지 여부를 지정 하려면이 라디오 단추 중 하나를 선택 `CTable` 또는 `CCommand` (기본값).  
  
 **테이블**  
 사용 하려는 경우이 옵션을 선택 `CTable` 또는 **db_table** 를 클래스 선언 테이블과 테이블 접근자를 만듭니다.  
  
 **명령**  
 사용 하려는 경우이 옵션을 선택 `CCommand` 또는 **db_command** 명령 및 명령 접근자 클래스 선언을 만들려면 합니다. 이 기본적으로 선택 합니다.  
  
 **지원**  
 소비자 (기본값은 없음)에서 지원 해야 하는 업데이트 종류를 지정 하는 확인란을 선택 합니다. 다음에 설정 [DBPROP_IRowsetChange](https://msdn.microsoft.com/library/ms715892.aspx) 와 적절 한 항목을 [DBPROP_UPDATABILITY](https://msdn.microsoft.com/library/ms722676.aspx) 속성에서 지도 설정 합니다.  
  
 **변경**  
 지정 소비자 행 집합의 행 데이터 업데이트를 지원 합니다.  
  
 **삽입**  
 소비자는 행 집합에 행 삽입을 지원 하는지 지정 합니다.  
  
 **삭제**  
 소비자는 행 집합에서 행 삭제를 지원 하는지 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL OLE DB 소비자](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [연결 문자열 및 데이터 연결 (OLE DB)](https://msdn.microsoft.com/library/ms718376.aspx)

