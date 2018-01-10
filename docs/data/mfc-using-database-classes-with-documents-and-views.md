---
title: "MFC: 문서 및 뷰를 이용한 데이터베이스 클래스를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [C++], database applications
- recordsets [C++], documents and views
- CRecordView class, using in database forms
- views [C++], database applications
- forms [C++], database applications
- record views [C++], form-based applications
- document/view architecture [C++], in databases
- database applications [C++], forms
- database classes [C++], MFC
- ODBC recordsets [C++], documents and views
- ODBC [C++], forms
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d3e2286c10d83b25576474692b5a7faeb9bb332
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용
문서/뷰 아키텍처 유무는 MFC 데이터베이스 클래스를 사용할 수 있습니다. 이 항목에는 문서 및 뷰 작업을 강조합니다. 설명합니다.  
  
-   [폼 기반 응용 프로그램을 작성 하는 방법](#_core_writing_a_form.2d.based_application) 를 사용 하는 `CRecordView` 개체 변수로 문서에 있는 기본 보기입니다.  
  
-   [문서 및 뷰 recordset 개체를 사용 하는 방법](#_core_using_recordsets_in_documents_and_views)합니다.  
  
-   [기타 고려 사항](#_core_other_factors)합니다.  
  
 대체 방법에 대 한 참조 [MFC: 문서 데이터베이스 클래스를 사용 하 여 뷰와](../data/mfc-using-database-classes-without-documents-and-views.md)합니다.  
  
##  <a name="_core_writing_a_form.2d.based_application"></a>폼 기반 응용 프로그램을 작성  
 여러 데이터 액세스 응용 프로그램 폼을 기반으로 합니다. 사용자 인터페이스는 사용자 검사, 입력, 또는 데이터 편집 컨트롤을 포함 하는 폼입니다. 기반 응용 프로그램 폼을 하려면 클래스를 사용 하 여 `CRecordView`합니다. MFC 응용 프로그램 마법사를 실행 하 고 선택 **ODBC** 클라이언트 형식을 **데이터베이스 지원** 페이지, 프로젝트에서는 `CRecordView` 뷰 클래스에 대 한 합니다.
  
 폼 기반 응용 프로그램에서 각 레코드 뷰 개체에 대 한 포인터를 저장 한 `CRecordset` 개체입니다. 레코드 집합 및 데이터 원본 간에 데이터를 교환 하는 프레임 워크의 레코드 필드 교환 (RFX) 메커니즘입니다. 대화 상자 데이터 교환 (DDX) 메커니즘 recordset 개체의 필드 데이터 멤버와 폼의 컨트롤 간에 데이터를 교환 합니다. `CRecordView`또한 폼에 레코드를 탐색 하기 위한 기본 명령 처리기 함수를 제공 합니다.  
  
 응용 프로그램 마법사를 사용 하 여 폼 기반 응용 프로그램을 만들려면 참조 [폼 기반 MFC 응용 프로그램을 만드는](../mfc/reference/creating-a-forms-based-mfc-application.md) 및 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../mfc/reference/database-support-mfc-application-wizard.md)합니다.  
  
 폼의 전체 논의 알려면 [레코드 뷰](../data/record-views-mfc-data-access.md)합니다.  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a>레코드 집합을 문서 및 뷰를 사용 하 여  
 많은 단순 양식 기반 응용 프로그램에 문서를 사용할 필요가 없습니다. 응용 프로그램이 더 복잡 한 경우 데이터베이스에 대 한 문서를 프록시로 사용 하려고 하는 할 경우 저장 한 `CDatabase` 데이터 원본에 연결 하는 개체입니다. 일반적으로 폼 기반 응용 프로그램 보기에서 레코드 집합 개체에 대 한 포인터를 저장합니다. 레코드 집합을 저장 하는 다른 종류의 데이터베이스 응용 프로그램 및 `CDatabase` 문서에는 개체입니다. 다음은 일부의 문서를 사용 하 여 데이터베이스 응용 프로그램의 예입니다.  
  
-   로컬 컨텍스트에서 레코드 집합에 액세스 하는 경우 만들는 `CRecordset` 필요에 따라 문서 또는 보기의 멤버 함수에서 로컬로 개체입니다.  
  
     함수에서 지역 변수로 recordset 개체를 선언 합니다. 전달 **NULL** 프레임 워크를 만들고 임시 열 때문에 생성자 `CDatabase` 있습니다에 대 한 개체입니다. 대신 전달에 대 한 포인터는 `CDatabase` 개체입니다. 함수 내에서 레코드 집합을 사용 하 고 함수가 종료 될 때 자동으로 소멸 되도록 합니다.  
  
     전달 하는 경우 **NULL** recordset 생성자에 프레임 워크는 레코드 집합에서 반환 되는 정보를 사용 `GetDefaultConnect` 만들려는 멤버 함수는 `CDatabase` 개체를 엽니다. 마법사 구현 `GetDefaultConnect` 드립니다.  
  
-   레코드 집합의 문서에 사용 되는 동안에 액세스할 때는 하나 이상 포함 `CRecordset` 문서에 있는 개체입니다.  
  
     문서를 초기화할 때 또는 필요에 따라 recordset 개체를 생성 합니다. 이미 존재 하거나 생성 하 고 아직 존재 하지 않는 경우 레코드 집합을 열고 경우 레코드 집합에 대 한 포인터를 반환 하는 함수를 작성할 수 있습니다. 닫기, 삭제 하 고 필요에 따라 레코드 집합 다시 또는 호출의 **Requery** 레코드를 새로 고치려면 멤버 함수입니다.  
  
-   데이터 원본에 액세스 문서의 수명 동안을 포함 한 `CDatabase` 또는 개체에 대 한 포인터를 저장 한 `CDatabase` 개체가 합니다.  
  
     `CDatabase` 개체는 데이터 원본에 대 한 연결을 관리 합니다. 개체는 문서 생성 되는 동안 자동으로 생성 되며 호출 하면 해당 **열려** 문서를 초기화할 때 멤버 함수입니다. 문서에 대 한 포인터를 전달 하 문서 멤버 함수에서 레코드 집합 개체를 생성할 때 `CDatabase` 개체입니다. 각 레코드 집합 데이터 원본과 연결합니다. 데이터베이스 개체는 일반적으로 문서를 닫을 때 삭제 됩니다. 레코드 집합 개체는 함수의 범위를 벗어나면에 일반적으로 삭제 됩니다.  
  
##  <a name="_core_other_factors"></a>기타 요소  
 폼 기반 응용 프로그램 없어 많습니다 사용 되는 프레임 워크의 문서 serialization 메커니즘에 대 한 모든 않으므로 제거 하거나 비활성화 하거나 교체 해야 할 수는 `New` 및 **열려** 에 있는 명령을 **파일**메뉴. 문서 참조 [Serialization: Serialization vs. 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md)합니다.  
  
 만들 수도 있습니다는 프레임 워크를 지원할 수 있는 많은 사용자 인터페이스 기능을 활용 합니다. 예를 들어 여러 개 사용할 수 있습니다 `CRecordView` 분할자 창에 있는 개체 여러 문서 MDI (인터페이스) 자식 창, 및 등 다른 여러 레코드 집합을 엽니다.  
  
 보기에는 인쇄를 구현 하려는 경우, 양식을 사용 하 여 구현 인지 여부에 관계 `CRecordView` 어떤 것입니다. 파생 된 클래스 `CFormView`, `CRecordView` 않습니다 인쇄를 지원 하지 않지만 있습니다 재정의할 수는 `OnPrint` 멤버 함수를 인쇄할 수 있도록 합니다. 자세한 내용은 클래스를 참조 하십시오. [CFormView](../mfc/reference/cformview-class.md)합니다.  
  
 문서 및 뷰를 전혀 사용 하지 않을 수도 있습니다. 이 경우 참조 [MFC: 문서 데이터베이스 클래스를 사용 하 여 뷰와](../data/mfc-using-database-classes-without-documents-and-views.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 데이터베이스 클래스 (... / data/mfc-database-classes-odbc-and-dao.md)