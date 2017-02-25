---
title: "MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용 | Microsoft Docs"
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
  - "응용 프로그램 마법사[C++], 데이터베이스 응용 프로그램 만들기"
  - "CDaoRecordView 클래스, 데이터베이스 응용 프로그램에서 사용"
  - "CRecordView 클래스, 데이터베이스 응용 프로그램에서 사용"
  - "DAO[C++], 데이터베이스 응용 프로그램의 파일 지원"
  - "DAO[C++], 응용 프로그램 작성"
  - "데이터베이스 응용 프로그램[C++], 응용 프로그램 마법사 옵션"
  - "데이터베이스 응용 프로그램[C++], 문서 없이 사용"
  - "데이터베이스 응용 프로그램[C++], 뷰 없이 사용"
  - "데이터베이스 클래스[C++], MFC"
  - "문서/뷰 아키텍처[C++], 데이터베이스"
  - "문서[C++], 응용 프로그램"
  - "파일[C++], MFC"
  - "ODBC[C++], 데이터베이스 응용 프로그램의 파일 지원"
  - "ODBC 응용 프로그램[C++]"
  - "ODBC 응용 프로그램[C++], 문서 없이 사용"
  - "ODBC 응용 프로그램[C++], 뷰 없이 사용"
  - "사용자 인터페이스[C++], 그리기 정보"
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터베이스 응용 프로그램에서는 프레임워크의 문서\/뷰 아키텍처를 사용하지 않을 수도 있습니다.  다음은 이 항목에서 설명하는 내용입니다.  
  
-   문서 serialization 같은 [문서가 필요 없는 경우](#_core_when_you_don.92.t_need_documents)  
  
-   **새로 만들기**, **열기**, **저장** 및 **다른 이름으로 저장** 등의 문서 관련 **파일** 메뉴 명령과 serialization을 사용하지 않고 응용 프로그램을 지원하기 위한 [응용 프로그램 마법사 옵션](#_core_appwizard_options_for_documents_and_views)  
  
-   [최소한의 문서를 사용하는 응용 프로그램 작업 방법](#_core_applications_with_minimal_documents)  
  
-   [문서나 뷰를 사용하지 않는 응용 프로그램 구성 방법](#_core_applications_with_no_document)  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a> 문서가 필요 없는 경우  
 일부 응용 프로그램에는 문서라는 뚜렷한 개념이 있습니다.  보통 이러한 응용 프로그램에서는 **파일 열기** 명령을 이용해 저장소에 있는 파일을 모두 또는 대부분 메모리에 로드할 수 있습니다.  이러한 응용 프로그램에서는 **파일 저장** 또는 **다른 이름으로 저장** 명령을 사용하면 업데이트된 모든 파일을 한 번에 저장소에 다시 쓸 수 있습니다.  이렇게 되면 사용자는 데이터 파일을 볼 수 있습니다.  
  
 그러나, 어떤 응용 프로그램에서는 문서가 필요하지 않습니다.  데이터베이스 응용 프로그램은 트랜잭션을 기준으로 작동합니다.  이러한 응용 프로그램은 데이터베이스에서 여러 레코드를 선택하여 사용자에게 대개 한 번에 하나씩 표시합니다.  대개 사용자는 메모리에 하나만 있을 수 있는 단일 현재 레코드를 볼 수 있습니다.  
  
 사용 중인 응용 프로그램에서 데이터 저장을 위한 문서가 필요하지 않은 경우에는 프레임워크의 문서\/뷰 아키텍처 중 일부 또는 모두가 불필요하게 됩니다.  불필요한 정도는 접근 방법에 따라 달라집니다.  다음과 같은 경우가 있습니다.  
  
-   데이터 소스에 대한 연결을 저장하는 장소로 최소한의 문서를 사용하지만 serialization과 같은 일반 문서 기능은 사용하지 않습니다.  이러한 방식은 여러 데이터 뷰가 필요하고 이 뷰를 모두 동기화하여 한꺼번에 업데이트할 경우에 유용합니다.  
  
-   뷰를 이용하지 않고, 직접 그리는 프레임 창을 이용할 수 있습니다.  이 경우에는 문서 대신 프레임 창 개체에 데이터나 데이터 연결을 저장할 수 있습니다.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a> 문서 및 뷰에 대한 응용 프로그램 마법사 옵션  
 MFC 응용 프로그램 마법사의 **데이터베이스 지원 선택**에는 몇 가지 옵션이 제공됩니다. 이러한 옵션에 대해서는 아래의 테이블에 나와 있습니다.  MFC 응용 프로그램 마법사를 이용해 응용 프로그램을 만드는 경우에 이러한 옵션을 이용하면 응용 프로그램에 문서와 뷰가 포함됩니다.  일부 옵션은 필요 없는 문서 기능을 생략한 문서 및 뷰를 제공합니다.  자세한 내용은 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../mfc/reference/database-support-mfc-application-wizard.md)을 참조하십시오.  
  
|옵션|보기|Document|  
|--------|--------|--------------|  
|**없음**|`CView`에서 파생됩니다.|데이터베이스를 지원하지 않습니다.  기본 옵션입니다.<br /><br /> [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서\/뷰 아키텍처 지원** 옵션을 선택하면 **파일** 메뉴의 `New`, **열기**, **저장** 및 **다른 이름으로 저장** 명령과 serialization과 같은 모든 문서 지원을 받게 됩니다.  [문서를 사용하지 않는 응용 프로그램](#_core_applications_with_no_document)을 참조하십시오.|  
|**헤더 파일만**|`CView`에서 파생됩니다.|응용 프로그램에 기본적인 수준의 데이터베이스 지원을 제공합니다.<br /><br /> Afxdb.h를 포함합니다.  링크 라이브러리를 추가하지만 데이터베이스 관련 클래스를 만들지는 않습니다.  나중에 레코드 집합을 만들어 레코드를 조사하고 업데이트하는 데 사용할 수 있습니다.|  
|**파일을 지원하지 않는 데이터베이스 뷰**|`CRecordView`에서 파생|문서 지원은 제공하지만 serialization은 지원하지 않습니다.  문서에는 레코드 집합을 저장할 수 있고 다중 뷰를 통합할 수 있습니다. `New`, **열기**, **저장** 및 **다른 이름으로 저장** 명령 또는 serialization을 지원하지 않습니다.  [최소한의 문서를 사용하는 응용 프로그램](#_core_applications_with_minimal_documents)을 참조하십시오.  데이터베이스 뷰를 포함하려면 데이터 소스를 지정해야 합니다.<br /><br /> 데이터베이스 헤더 파일, 연결 라이브러리, 레코드 뷰 및 레코드 집합이 포함됩니다. 이 옵션은 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서\/뷰 아키텍처 지원** 옵션을 선택한 경우에만 사용할 수 있습니다.|  
|**파일을 지원하는 데이터베이스 뷰**|`CRecordView`에서 파생|문서와 관련된 **파일** 메뉴 명령 및 serialization과 같은 문서 지원을 모두 제공합니다.  일반적으로 데이터베이스 응용 프로그램은 파일 단위보다는 레코드 단위로 실행되므로 serialization 작업이 필요하지 않습니다.  그러나, serialization을 사용해야 하는 특별한 경우도 있습니다.  [최소한의 문서를 사용하는 응용 프로그램](#_core_applications_with_minimal_documents)을 참조하십시오.  데이터베이스 뷰를 포함하려면 데이터 소스를 지정해야 합니다.<br /><br /> 데이터베이스 헤더 파일, 연결 라이브러리, 레코드 뷰 및 레코드 집합이 포함됩니다. 이 옵션은 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서\/뷰 아키텍처 지원** 옵션을 선택한 경우에만 사용할 수 있습니다.|  
  
 serialization의 대체 방법과 serialization의 다른 용도에 대해서는 [Serialization: Serialization과 데이터베이스 입출력 비교](../mfc/serialization-serialization-vs-database-input-output.md)을 참조하십시오.  
  
##  <a name="_core_applications_with_minimal_documents"></a> 최소한의 문서를 사용하는 응용 프로그램  
 MFC 응용 프로그램 마법사에는 폼 기반 데이터 액세스 응용 프로그램을 지원하는 옵션이 두 가지 있습니다.  각 옵션은 `CRecordView` 파생 뷰 클래스 및 문서를 만듭니다.  이 두 가지 옵션의 차이점은 문서에서 제외하는 내용이 다르다는 것입니다.  
  
###  <a name="_core_a_document_without_file_support"></a> 파일을 지원하지 않는 문서  
 문서 serialization이 불필요한 경우에는 응용 프로그램 마법사 데이터베이스 옵션에서 **파일을 지원하지 않는 데이터베이스 뷰**를 선택합니다.  파일을 지원하지 않는 문서는 다음과 같은 목적으로 유용하게 사용할 수 있습니다.  
  
-   `CRecordset` 개체를 편리하게 저장할 수 있습니다.  
  
     이러한 용도는 다음과 같은 일반적인 문서 개념과 유사합니다. 즉, 문서는 데이터 또는 레코드 세트를 저장하며, 뷰는 곧 문서의 뷰를 말합니다.  
  
-   응용 프로그램에서 다중 레코드 뷰와 같은 다중 뷰를 제공하는 경우 문서는 다중 뷰 조정 기능을 지원합니다.  
  
     다중 뷰에 동일한 데이터가 표시되는 경우, 특정 뷰에서 데이터가 변경되면 `CDocument::UpdateAllViews` 멤버 함수를 이용해 모든 뷰에 대한 업데이트를 조정할 수 있습니다.  
  
 이 옵션은 일반적으로 간단한 폼 기반 응용 프로그램에 사용합니다.  응용 프로그램 마법사에서는 이러한 응용 프로그램을 자동으로 만들 수 있는 편리한 구조를 제공합니다.  
  
###  <a name="_core_a_document_with_file_support"></a> 파일을 지원하는 문서  
 문서 관련 **File** 메뉴 명령과 문서 serialization이 필요한 경우에는 응용 프로그램 마법사 데이터베이스 옵션에서 이 메뉴를 지원하는 **데이터베이스 뷰**를 선택합니다.  사용 중인 프로그램의 데이터 액세스 부분에 대해 [파일을 지원하지 않는 문서](#_core_a_document_without_file_support)에 나와 있는 것과 같은 방식으로 문서를 사용할 수 있습니다.  예를 들어, 문서의 serialization 기능을 이용하여 사용자의 필요 사항이나 기타 유용한 정보를 저장하는 serialize된 사용자 프로필 문서를 읽고 쓸 수 있습니다.  자세한 내용은 [Serialization: Serialization과 데이터베이스 입출력 비교](../mfc/serialization-serialization-vs-database-input-output.md)을 참조하십시오.  
  
 응용 마법사에서 이 옵션을 지원하기는 하지만 문서를 serialize하는 코드는 사용자가 직접 작성해야 합니다.  serialize된 정보는 문서 데이터 멤버에 저장합니다.  
  
##  <a name="_core_applications_with_no_document"></a> 문서를 사용하지 않는 응용 프로그램  
 경우에 따라서는 문서나 뷰를 사용하지 않는 응용 프로그램을 작성할 수도 있습니다.  문서가 없는 경우 `CRecordset` 개체 등의 데이터는 프레임 창 클래스나 응용 프로그램 클래스에 저장합니다.  응용 프로그램에서 사용자 인터페이스를 제공하는지에 따라 추가 요구 사항이 다릅니다.  
  
###  <a name="_core_database_support_with_a_user_interface"></a> 사용자 인터페이스를 제공하는 데이터베이스 지원  
 콘솔 명령줄 인터페이스과 같은 사용자 인터페이스가 있는 경우 응용 프로그램은 뷰가 아닌 프레임 창의 클라이언트 영역을 직접 사용합니다.  이러한 응용 프로그램에서는 기본 사용자 인터페이스에 대해서 `CRecordView`, `CFormView` 또는 `CDialog`를 사용하지 않지만 보통 일반 대화 상자에 대해서는 `CDialog`를 사용합니다.  
  
###  <a name="_core_writing_applications_without_documents"></a> 문서를 사용하지 않는 응용 프로그램 작성  
 응용 프로그램 마법사에서는 문서를 사용하지 않는 응용 프로그램 생성을 지원하지 않기 때문에 고유한 `CWinApp` 파생 클래스를 작성해야 하며, 필요한 경우 `CFrameWnd`나 `CMDIFrameWnd` 클래스를 만들어야 합니다.  `CWinApp::InitInstance`를 재정의하고 응용 프로그램 개체를 다음과 같이 선언합니다.  
  
```  
CYourNameApp theApp;  
```  
  
 프레임워크에서는 메시지 매핑 메커니즘 및 기타 여러 가지 기능을 제공합니다.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a> 사용자 인터페이스와 분리된 데이터베이스 지원  
 일부 응용 프로그램에서는 사용자 인터페이스가 전혀 필요 없거나 한 개만 있으면 됩니다.  예를 들어, 다음과 같은 경우입니다.  
  
-   다른 응용 프로그램\(클라이언트\)에서 응용 프로그램과 데이터 소스간에 데이터를 특수 처리하는 데 필요한 중간 데이터 액세스 개체를 작성하는 경우  
  
-   사용자 작업 없이도 데이터를 처리하는 응용 프로그램을 작성하는 경우. 예를 들어, 특정 데이터베이스 형식에서 다른 형식으로 데이터를 변환하는 응용 프로그램이나 계산 및 일괄 업데이트를 수행하는 응용 프로그램.  
  
 `CRecordset` 또는 `CDaoRecordset` 개체를 소유한 문서가 없기 때문에, `CWinApp` 파생 응용 프로그램 클래스에 해당 개체를 포함 데이터 멤버로 저장할 수도 있습니다.  대신 다음과 같은 방법을 사용할 수도 있습니다.  
  
-   영구적인 `CRecordset` 또는 `CDaoRecordset` 개체를 보관하지 않습니다.  이렇게 하려면 레코드 집합 클래스 생성자에 **NULL**을 전달하면 됩니다.  이 경우, 프레임워크에서는 레코드 집합의 `GetDefaultConnect` 멤버 함수에 포함된 정보를 이용하여 임시로 `CDatabase` 또는 `CDaoDatabase` 개체를 만듭니다.  이 방법이 아래 방법보다 좀더 쉽습니다.  
  
-   `CRecordset` 또는 `CDaoRecordset` 개체를 전역 변수로 만듭니다.  이 변수는 `CWinApp::InitInstance` 재정의에서 동적으로 생성된 레코드 집합 개체에 대한 포인터이어야 합니다.  결과적으로 이것은 프레임워크가 초기화되기 전에 개체가 생성되지 않도록 합니다.  
  
-   문서 또는 뷰의 컨텍스트 내에서와 마찬가지로 레코드 집합 개체를 사용합니다.  응용 프로그램이나 프레임 창 개체의 멤버 함수로 레코드 집합을 만듭니다.  
  
## 참고 항목  
 [MFC 데이터베이스 클래스\(ODBC 및 DAO\)](../data/mfc-database-classes-odbc-and-dao.md)