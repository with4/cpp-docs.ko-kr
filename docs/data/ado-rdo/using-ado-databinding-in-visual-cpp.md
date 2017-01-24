---
title: "Visual C++에서 ADO 데이터 바인딩 사용 | Microsoft Docs"
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
  - "ADO[C++], 데이터 바인딩"
  - "바인딩 컨트롤[C++], ADO"
  - "바인딩 컨트롤[C++], RDO"
  - "데이터 바인딩[C++], ADO"
  - "데이터 바인딩[C++], RDO"
ms.assetid: ad193919-3437-41ee-b41c-9d353f6274e5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++에서 ADO 데이터 바인딩 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서 ADO 데이터 바인딩을 사용하려면 다음 작업을 수행해야 합니다.  
  
-   ADO 데이터 컨트롤을 추가합니다.  
  
-   데이터 소스를 가리킵니다.  
  
-   레코드 원본\(SQL 쿼리나 데이터 검색어\)을 지정합니다.  
  
-   ADO 데이터 바인딩 컨트롤을 추가합니다.  
  
-   ADO 데이터 컨트롤에 데이터 바인딩 컨트롤을 연결합니다.  
  
-   ADO 데이터 컨트롤의 레코드 원본에 바인딩할 필드를 선택합니다.  
  
### Visual C\+\+에서 ADO 데이터 바인딩을 사용하려면  
  
1.  MFC 응용 프로그램 마법사를 사용하여 MFC 대화 상자 응용 프로그램이나 MFC 폼 뷰 응용 프로그램을 만듭니다.  
  
2.  대화 상자에 Microsoft ADO 데이터 컨트롤을 추가합니다\([Visual C\+\+ 응용 프로그램에 컨트롤 삽입](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) 참조\).  
  
3.  ADO 데이터 컨트롤이 OLE DB 데이터 소스를 가리키도록 합니다.  
  
    1.  마우스 오른쪽 단추로 ADO 데이터 컨트롤을 클릭한 다음 **속성**을 클릭합니다.  
  
    2.  **컨트롤** 탭에서 **연결 문자열 사용**을 클릭합니다.  제공된 공급자를 사용하거나 삭제할 수 있습니다.  
  
    3.  **빌드**를 클릭합니다.  **연결 문자열 사용**에서 공급자를 삭제한 경우에는 공급자를 새로 정의할 수 있습니다.  공급자를 정의한 다음 ADO 데이터 컨트롤의 속성에 다시 액세스하고 **빌드**를 다시 선택하여 작업을 계속합니다.  
  
         **빌드**를 선택하기 전에 **연결 문자열 사용**에서 공급자를 정의하면 데이터 연결 속성을 정의할 수 있습니다.  그러면 DataLink 마법사가 표시됩니다.  
  
    4.  필요하면 **공급자**를 변경하고 공급자에 적절한 **위치**와 **데이터 소스** 값을 정의합니다.  예를 들어, SQL Server 공급자를 사용할 경우에는 **위치**에서 데이터베이스 서버를 지정하고 **데이터 소스**에서 데이터베이스를 지정합니다.  ODBC 공급자를 사용할 경우에는 **데이터 소스**가 ODBC DSN에 해당합니다.  
  
    5.  **인증** 탭을 클릭하고, 데이터 소스에 필요하면 **사용자 이름**과 **암호**의 값을 설정합니다.  
  
    6.  **연결** 탭을 클릭하고 **연결 테스트**를 클릭하여 데이터 소스를 테스트합니다.  결과 창의 끝으로 스크롤하여 테스트에 성공했는지 확인합니다.  실패했으면 데이터 소스의 구성을 확인합니다.  암호를 잘못 입력했거나 **위치**와 **데이터 소스** 필드에 잘못된 값을 입력하는 등의 일반적인 오류 때문에 테스트가 실패할 수 있습니다.  
  
    7.  DataLink 마법사를 끝내고 ADO 데이터 컨트롤의 속성 시트로 돌아갑니다.  
  
4.  `RecordSource` 탭에서 **명령 텍스트\(SQL\)**에 쿼리를 입력합니다.  데이터 바인딩 컨트롤은 이 쿼리의 결과에 바인딩할 수 있습니다.  쿼리는 일반적으로 SQL입니다.  SQL을 사용하지 않는 OLE DB 공급자도 있습니다.  
  
5.  필요하면 다른 ADO 데이터 컨트롤의 속성을 설정하고 ADO 데이터 컨트롤의 속성 시트를 닫습니다.  
  
6.  데이터 바인딩 컨트롤을 추가합니다.  예를 들어, RDO DBGrid 컨트롤과는 다른 DataGrid 컨트롤을 추가합니다.  
  
7.  DataGrid의 속성을 설정합니다.  
  
    1.  DataGrid를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
    2.  **모두** 탭을 클릭하고 **DataSource** 속성을 ADO 데이터 컨트롤로 설정합니다.  **DataSource** 드롭다운 목록을 클릭하고 ADO 데이터 컨트롤의 ID를 찾습니다.  기본 ID 이름은 IDC\_ADODC1입니다.  
  
8.  테스트 모드에서 실행하려면 Ctrl\+T를 누릅니다.  데이터를 스크롤할 수 있습니다.  테스트 모드를 끝내려면 Esc 키를 누르거나 대화 상자를 닫습니다.  
  
 프로그램을 컴파일하고 실행할 경우에도 데이터를 스크롤할 수 있습니다.  
  
## 참고 항목  
 [ADO 데이터 바인딩](../../data/ado-rdo/ado-databinding.md)   
 [Visual C\+\+에서 ActiveX 컨트롤을 사용하여 데이터 바인딩](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)