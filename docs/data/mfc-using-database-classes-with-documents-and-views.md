---
title: "MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용 | Microsoft Docs"
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
  - "CDaoRecordView 클래스, 데이터베이스 응용 프로그램에서 사용"
  - "CDaoRecordView 클래스, 데이터베이스 폼에서 사용"
  - "CRecordView 클래스, 데이터베이스 폼에서 사용"
  - "DAO[C++], 데이터베이스 응용 프로그램의 폼"
  - "DAO 레코드 집합[C++]"
  - "DAO 레코드 집합[C++], 문서 및 뷰"
  - "데이터베이스 응용 프로그램[C++], 폼"
  - "데이터베이스 클래스[C++], MFC"
  - "문서/뷰 아키텍처[C++], 데이터베이스"
  - "문서[C++], 데이터베이스 응용 프로그램"
  - "폼[C++], 데이터베이스 응용 프로그램"
  - "ODBC[C++], 폼"
  - "ODBC 레코드 집합[C++], 문서 및 뷰"
  - "레코드 뷰[C++], 폼 기반 응용 프로그램"
  - "레코드 집합[C++], 문서 및 뷰"
  - "뷰[C++], 데이터베이스 응용 프로그램"
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 데이터베이스 클래스, 즉 DAO 또는 ODBC를 사용할 경우에는 문서\/뷰 아키텍처를 사용할 수도 있고 사용하지 않을 수도 있습니다.  그러나 이 항목에서는 문서 및 뷰를 사용하는 방식을 중점적으로 다룹니다.  그 내용은 다음과 같습니다.  
  
-   문서에서 기본 뷰로 `CRecordView` 또는 `CDaoRecordView` 개체를 사용하여 [폼 기반 응용 프로그램을 작성하는 방법](#_core_writing_a_form.2d.based_application)  
  
-   [문서와 뷰에서 레코드 집합 개체를 사용하는 방법](#_core_using_recordsets_in_documents_and_views)  
  
-   [기타 고려 사항](#_core_other_factors)  
  
 다른 방법은 [MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용](../data/mfc-using-database-classes-without-documents-and-views.md)을 참조하십시오.  
  
##  <a name="_core_writing_a_form.2d.based_application"></a> 폼 기반 응용 프로그램 작성  
 대부분의 데이터 액세스 응용 프로그램은 폼을 기반으로 합니다.  사용자 인터페이스란 사용자가 데이터를 검사, 입력 또는 편집할 수 있는 컨트롤이 포함된 폼을 말합니다.  응용 프로그램을 폼 기반으로 만들려면 `CRecordView` 또는 `CDaoRecordView` 클래스를 사용합니다 .  MFC 응용 프로그램 마법사를 실행한 다음, **데이터베이스 지원** 페이지에서 **ODBC** 클라이언트 형식을 선택하면 해당 프로젝트는 뷰 클래스에 `CRecordView`를 사용합니다.  MFC 마법사에서는 이제 DAO를 지원하지 않습니다. 따라서, `CDaoRecordView`를 사용하려면 사용자가 직접 CDaoREcordView 클래스에 대한 코드를 작성해야 합니다.  
  
 폼 기반 응용 프로그램에서는 각 레코드 뷰 개체가 `CRecordset` 또는 `CDaoRecordset` 개체에 대한 포인터를 저장합니다.  프레임워크의 RFX\(레코드 필드 교환\) 메커니즘은 레코드 집합과 데이터 소스 간에 데이터를 교환합니다.  DDX\(대화 상자 데이터 교환\) 메커니즘은 레코드 집합 개체의 필드 데이터 멤버와 폼의 컨트롤 사이에 데이터를 교환합니다.  `CRecordView` 또는 `CDaoRecordView`에서도 폼의 레코드 간에 이동하기 위한 기본 명령 처리기 함수를 제공합니다.  
  
 응용 프로그램 마법사를 사용하여 폼 기반 응용 프로그램을 만들려면 [폼 기반 MFC 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md) 및 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../mfc/reference/database-support-mfc-application-wizard.md)을 참조하십시오.  
  
 폼에 대한 자세한 내용은 [레코드 뷰](../data/record-views-mfc-data-access.md)를 참조하십시오.  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a> 문서 및 뷰에서 레코드 집합 사용  
 대부분의 단순한 폼 기반 응용 프로그램에는 문서가 필요하지 않습니다.  사용중인 응용 프로그램이 보다 복잡하다면, 데이터베이스에 대한 프록시로 문서를 이용하여 데이터 소스에 연결된 `CDatabase`나 `CDaoDatabase` 개체를 저장해야 합니다.  폼 기반 응용 프로그램은 대부분 뷰에 레코드 집합 개체에 대한 포인터를 저장합니다.  다른 종류의 데이터베이스 응용 프로그램은 문서에 레코드 집합과 `CDatabase` 또는 `CDaoDatabase` 개체를 저장합니다.  다음은 데이터베이스 응용 프로그램에서 문서를 이용하는 몇 가지 예입니다.  
  
-   로컬 컨텍스트에서 레코드 집합에 액세스하려면, 문서나 뷰의 멤버 함수로 `CRecordset` 또는 `CDaoRecordset` 개체를 로컬에서 만들어야 합니다.  
  
     레코드 집합 개체는 함수의 지역 변수로 선언합니다.  생성자에 **NULL**을 전달합니다. 그러면, 프레임워크에서 임시 `CDatabase`나 `CDaoDatabase` 개체를 자동으로 만듭니다.  아니면, `CDatabase`나 `CDaoDatabase`개체에 포인터를 전달합니다.  함수 안에서 레코드 집합을 사용하고, 함수가 종료되면 레코드 집합이 자동으로 소멸되도록 합니다.  
  
     레코드 집합 생성자에 **NULL**을 전달하면, 프레임워크에서는 레코드 집합의 `GetDefaultConnect` 멤버 함수에서 반환한 정보를 이용해 `CDatabase`나 `CDaoDatabase`개체를 만들어 이를 엽니다.  `GetDefaultConnect`는 마법사에서 자동으로 구현됩니다.  
  
-   문서의 사용 기간 중에 레코드 집합에 액세스하려면, 해당 문서에 `CRecordset` 또는 `CDaoRecordset` 개체를 하나 이상 포함합니다.  
  
     문서를 초기화하거나 필요한 경우에 레코드 집합 개체를 생성합니다.  레코드 집합이 있는 경우에는 포인터를 레코드 집합에 반환하는 함수를 작성하고, 레코드 집합이 없는 경우에는 레코드 집합을 생성하여 이를 여는 함수를 작성합니다.  필요한 경우 레코드 집합을 닫고 삭제한 후 다시 만들거나, 레코드 집합 **Requery** 멤버 함수를 호출하여 레코드를 새로 고칩니다.  
  
-   문서의 사용 기간 중에 데이터 소스에 액세스하려면, 해당 문서에 `CDatabase`또는 `CDaoDatabase` 개체를 포함하거나 `CDatabase` 또는 `CDaoDatabase` 개체에 대한 포인터를 저장합니다.  
  
     `CDatabase`나 `CDaoDatabase` 개체는 데이터 소스에 대한 연결을 관리합니다.  이 개체는 문서 생성 과정에서 자동으로 생성되며, 문서를 초기화할 때 개체의 **Open** 멤버 함수를 호출합니다.  문서 멤버 함수에서 레코드 집합 개체를 생성할 때는 문서의 `CDatabase`나 `CDaoDatabase` 개체에 포인터를 전달합니다.  이렇게 하면, 각 레코드 집합을 해당 데이터 소스에 연결할 수 있습니다.  대부분의 경우 문서가 닫히면 데이터베이스 개체는 소멸됩니다.  보통 레코드 집합 개체는 함수의 범위를 벗어나면 소멸됩니다.  
  
##  <a name="_core_other_factors"></a> 기타 요소  
 폼 기반 응용 프로그램에서는 대개 프레임워크의 문서 serialization 메커니즘이 필요하지 않기 때문에, **파일** 메뉴의 `New` 및 **열기** 명령을 제거하거나, 비활성화하거나 바꿀 수 있습니다.  [Serialization: serialization 및 데이터베이스 입출력 비교](../mfc/serialization-serialization-vs-database-input-output.md) 문서를 참조하십시오.  
  
 이외에도, 프레임워크에서 지원할 수 있는 여러 사용자 인터페이스 기능을 이용할 수도 있습니다.  예를 들어, 분할 창에 있는 다중 `CRecordView` 또는 `CDaoRecordView` 개체를 이용할 수도 있고, 여러 MDI\(다중 문서 인터페이스\) 자식 창에 있는 다중 레코드 집합을 열 수도 있습니다.  
  
 현재 뷰에 포함된 모든 것은 `CRecordView`나 `CDaoRecordView` 중 어떤 것을 사용해 구현된 양식인지에 관계없이 인쇄해야 할 수도 있습니다.  `CFormView`, `CRecordView` 및 `CDaoRecordView` 에서 파생된 클래스는 인쇄를 지원하지 않지만, `OnPrint` 멤버 함수를 재정의하면 인쇄를 할 수 있습니다.  자세한 내용은 [CFormView](../mfc/reference/cformview-class.md) 클래스를 참조하십시오.  
  
 문서 및 뷰를 사용하지 않을 수도 있습니다.  이 경우 [MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용](../data/mfc-using-database-classes-without-documents-and-views.md)을 참조하십시오.  
  
## 참고 항목  
 [MFC 데이터베이스 클래스\(ODBC 및 DAO\)](../data/mfc-database-classes-odbc-and-dao.md)