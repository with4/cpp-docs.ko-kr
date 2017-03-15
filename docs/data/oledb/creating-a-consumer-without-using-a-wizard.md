---
title: "마법사를 사용하지 않고 소비자 만들기 | Microsoft Docs"
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
  - "OLE DB 소비자, 만들기"
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 마법사를 사용하지 않고 소비자 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제에서는 사용자가 기존 ATL 프로젝트에 OLE DB 소비자 지원 기능을 추가한다고 가정합니다.  OLE DB 소비자 지원 기능을 MFC 응용 프로그램에 추가하려면, 필요한 모든 지원 기능을 만들고 응용 프로그램을 실행하는 데 필요한 MFC 루틴을 호출하는 MFC 응용 프로그램 마법사를 실행해야 합니다.  
  
 ATL OLE DB 소비자 마법사를 사용하지 않고 OLE DB 소비자 지원 기능을 추가하려면:  
  
-   Stdafx.h 파일에 다음 `#include` 문을 추가합니다.  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 소비자는 프로그래밍 방식을 사용하여 작업을 대개 다음 순서대로 수행합니다.  
  
-   열을 지역 변수에 바인딩하는 사용자 레코드 클래스를 만듭니다.  이 예제에서는 `CMyTableNameAccessor`가 사용자 레코드 클래스입니다\([사용자 레코드](../../data/oledb/user-records.md) 참조\).  이 클래스에는 열 맵과 매개 변수 맵이 있습니다.  열 맵에서 지정한 각 필드에 대한 사용자 레코드 클래스에서 데이터 멤버를 선언합니다. 이들 각각의 데이터 멤버에 대해 상태 데이터 멤버와 길이 데이터 멤버도 선언합니다.  자세한 내용은 [마법사 생성 접근자의 필드 상태 데이터 멤버](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)를 참조하십시오.  
  
    > [!NOTE]
    >  자체 소비자를 작성하는 경우 데이터 변수가 상태 변수와 길이 변수 앞에 와야 합니다.  
  
-   데이터 소스 및 세션을 인스턴스화합니다.  사용할 행 집합과 접근자의 형식을 정하고 [CCommand](../../data/oledb/ccommand-class.md)나 [CTable](../../data/oledb/ctable-class.md)을 사용하여 행 집합을 인스턴스화합니다.  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor> >  
    ```  
  
-   **CoInitialize**를 호출하여 COM을 초기화합니다.  CoUnInitialize는 주로 main 코드에서 호출됩니다.  예를 들면 다음과 같습니다.  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Call [CDataSource::Open](../../data/oledb/cdatasource-open.md) or one of its variations.  
  
-   데이터 소스에 연결하고 세션을 연 후, 행 집합을 열어 초기화합니다.  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   옵션으로 `CDBPropSet::AddProperty`를 사용하여 행 집합 속성을 설정하고 `rs.Open`에 대한 매개 변수로 전달할 수 있습니다.  이 작업을 수행하는 방법에 대한 예제는 [소비자 마법사 생성 메서드](../../data/oledb/consumer-wizard-generated-methods.md)의 GetRowsetProperties를 참조하십시오.  
  
-   이제 데이터를 검색하거나 조작하기 위해 행 집합을 사용할 수 있습니다.  
  
-   응용 프로그램이 다 작성되면 연결, 세션 및 행 집합을 닫습니다.  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     명령을 사용하는 경우 **Close** 다음에 `ReleaseCommand`를 호출할 수 있습니다.  [CCommand::Close](../../data/oledb/ccommand-close.md)에 있는 코드 예제에서는 **Close** 및 `ReleaseCommand` 호출 방법을 보여 줍니다.  
  
-   **CoUnInitialize**를 호출하여 COM을 초기화하지 않습니다.  CoUnInitialize는 주로 main 코드에서 호출됩니다.  
  
    ```  
    CoUninitialize();  
    ```  
  
## 참고 항목  
 [OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer.md)