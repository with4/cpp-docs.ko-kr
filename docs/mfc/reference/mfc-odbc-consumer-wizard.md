---
title: "MFC ODBC 소비자 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.consumer.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ODBC 소비자 마법사"
  - "마법사[MFC]"
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC ODBC 소비자 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여기에 "검색 결과" 요약을 삽입합니다.  
  
 이 마법사에서는 지정한 데이터 소스에 액세스하는 데 필요한 ODBC 레코드 집합 클래스와 데이터 바인딩을 설정합니다.  
  
## UI 요소 목록  
 **데이터 소스**  
 **데이터 소스** 단추를 사용하면 지정된 ODBC 드라이버를 사용하여 지정된 데이터 소스를 설정할 수 있습니다.  데이터 소스 파일\(DSN\)에 대한 자세한 내용은 ODBC SDK의 [File Data Sources](https://msdn.microsoft.com/en-us/library/ms715401.aspx)를 참조하십시오.  **데이터 원본 선택** 대화 상자에는 다음과 같은 두 개의 탭이 있습니다.  
  
-   **파일 데이터 원본** 탭: **찾는 위치** 상자에서 데이터 소스로 사용할 파일을 선택하는 디렉터리를 지정합니다.  기본 디렉터리는 \\Program Files\\Common Files\\ODBC\\Data Sources입니다.  주 목록 상자에 기존 파일 데이터 소스\(.dsn 파일\)가 나타납니다.  [ODBC 데이터 소스 관리자](https://msdn.microsoft.com/en-us/library/ms714024.aspx)의 **파일 DSN** 탭을 사용하여 미리 데이터 소스를 설정하거나, 이 대화 상자를 사용하여 데이터 소스를 새로 만들 수 있습니다.  
  
     이 대화 상자에서 파일 데이터 소스를 새로 만들려면 `New`를 클릭하여 DSN 이름을 지정합니다. 그러면 **새 데이터 원본 만들기** 대화 상자가 나타납니다.  **새 데이터 원본 만들기** 대화 상자에서 해당하는 드라이버를 선택한 다음 `Next`과 **찾아보기**를 차례로 클릭하고 데이터 소스로 사용할 파일 이름을 선택합니다. .xls 파일과 같이 DSN이 아닌 파일을 표시하려면 모든 파일을 선택해야 합니다. 그런 후 `Next`을 클릭하고 **마침**을 클릭합니다. DSN이 아닌 파일을 선택한 경우 " ODBC Microsoft Excel 설정 " 대화 상자와 같이 드라이버에 따라 다른 대화 상자가 표시되는데, 이 대화 상자에서 파일을 DSN으로 변환합니다.  
  
    > [!NOTE]
    >  ODBC 데이터 소스 관리자를 사용하여 미리 파일 데이터 소스를 새로 만들 수도 있습니다.  **시작** 메뉴에서 **설정**, **제어판**, **관리 도구**, **데이터 원본\(ODBC\)** 및 **ODBC 데이터 소스 관리자**를 차례로 선택합니다.  
  
     **DSN 이름** 상자를 사용하면 파일 데이터 소스의 이름을 지정할 수 있습니다.  DSN 이름에는 해당하는 파일 확장명이 붙어야 합니다. Excel 파일의 경우에는 .xls, Access 파일의 경우에는 .mdb로 끝나야 합니다.  
  
     DSN에 대한 자세한 내용은 ODBC SDK의 [File Data Sources](https://msdn.microsoft.com/en-us/library/ms715401.aspx)를 참조하십시오.  
  
-   **컴퓨터 데이터 원본** 탭: 시스템 데이터 소스와 사용자 데이터 소스를 나열합니다.  사용자 데이터 소스는 시스템의 사용자에 따라 다릅니다.  이 시스템의 모든 사용자나 시스템 전역 서비스에서 시스템 데이터 소스를 사용할 수 있습니다.  ODBC SDK의 [컴퓨터 데이터 원본](https://msdn.microsoft.com/en-us/library/ms710952.aspx)을 참조하십시오.  
  
 ODBC 데이터 소스에 대한 자세한 내용은 ODBC SDK의 [Data Sources](https://msdn.microsoft.com/en-us/library/ms711688.aspx)를 참조하십시오.  
  
 마치려면 **확인**을 클릭합니다.  **데이터베이스 개체 선택** 대화 상자가 나타납니다.  이 대화 상자에서 소비자가 사용할 테이블이나 뷰를 선택합니다.  Ctrl 키를 누른 채로 항목을 클릭하여 여러 개의 뷰와 테이블을 선택할 수 있습니다.  
  
 **클래스**  
 선택한 파일 또는 컴퓨터 데이터 원본의 이름을 기본으로 하는 소비자 클래스의 이름입니다.  
  
 **.h 파일**  
 선택한 파일 또는 컴퓨터 데이터 원본의 이름을 기본으로 하는 소비자 클래스 헤더 파일의 이름입니다.  
  
 **.cpp 파일**  
 선택한 파일 또는 컴퓨터 데이터 원본의 이름을 기본으로 하는 소비자 클래스 구현 파일의 이름입니다.  
  
 **형식**  
 레코드 집합이 다이너셋\(기본값\)인지 스냅숏인지 지정합니다.  
  
-   **다이너셋**: 레코드 집합을 다이너셋으로 지정합니다.  다이너셋은 쿼리된 데이터베이스의 데이터에 인덱싱된 뷰를 제공하는 쿼리 결과입니다.  다이너셋은 정수 인덱스만 원본 데이터로 캐싱하므로 스냅숏에 대한 성능이 향상됩니다.  인덱스는 쿼리 결과로 검색된 모든 레코드를 직접 가리키고 레코드가 제거되었는지 여부를 나타냅니다.  쿼리한 레코드의 업데이트된 정보에도 액세스할 수 있습니다.  이 값이 기본값입니다.  
  
-   **스냅숏**: 레코드 집합을 스냅숏으로 지정합니다.  스냅숏은 쿼리 결과이며 특정 시점의 데이터베이스 뷰입니다.  쿼리 결과로 검색된 모든 레코드가 캐싱되므로 원본 레코드에 대한 변경 내용은 볼 수 없습니다.  
  
 **모든 열 바인딩**  
 선택된 테이블의 모든 열을 바인딩할지 여부를 지정합니다.  이 확인란을 선택하면\(기본값\) 모든 열이 바인딩됩니다. 이 확인란을 선택하지 않으면 열이 바인딩되지 않으므로 레코드 집합 클래스에서 사용자가 직접 바인딩해야 합니다.  
  
## 참고 항목  
 [MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)