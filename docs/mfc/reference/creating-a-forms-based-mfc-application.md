---
title: 폼 기반 MFC 응용 프로그램 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcforms.project
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5ee588d7fe90e5bfc39aa8e4ab7a7499b62ad98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-forms-based-mfc-application"></a>폼 기반 MFC 응용 프로그램 만들기
양식은은 사용자에 액세스 하 고 데이터를 변경할 수 있도록 하는 컨트롤이 있는 대화 상자입니다. 사용자 양식 중에서 선택이 선택 하는 응용 프로그램을 개발할 수도 있습니다. 폼 기반 응용 프로그램을 클릭 하 여 사용자 액세스 폼을 수 있습니다는 일반적으로 **새로** 에서 **파일** 메뉴. 사용자에 대 한 액세스를 제공 하지 않는 대화 상자 기반 응용 프로그램은 **새로** 옵션에 **파일** 메뉴는 폼 기반 응용 프로그램으로 간주 됩니다.  
  
 (SDI)에 단일 문서 인터페이스 폼 기반 응용 프로그램에 한 번에 실행할 수 있는 특정 폼의 인스턴스가 하나만 허용 합니다. 여러 폼에서 새 폼을 선택 하 여 SDI 폼 기반 응용 프로그램에서 동시에 실행할 수는 **새로** 옵션에 **파일** 메뉴.  
  
 다중 문서 인터페이스 mdi (다중) 폼 기반 응용 프로그램을 만드는 경우 응용 프로그램 같은 폼의 여러 인스턴스를 지원할 수 있게 됩니다.  
  
 다중 최상위 문서 기능과 응용 프로그램을 만들 문서에 대 한 암시적 부모인 바탕 화면 및 문서 프레임은 응용 프로그램의 클라이언트 영역에 제한 되지 않습니다. 문서는 자체 프레임, 메뉴 및 작업 표시줄 아이콘 각각의 여러 인스턴스를 열 수 있습니다. 하지만 선택 하는 경우 문서 인스턴스를 개별적으로 닫을 수도 있습니다는 `Exit` 옵션에서 **파일** 메뉴는 초기 인스턴스 응용 프로그램의 모든 인스턴스를 닫습니다.  
  
 SDI, MDI 및 다중 최상위 문서 응용 프로그램은 모든 폼 기반으로 하며 문서/뷰 아키텍처를 사용 합니다.  
  
 모든 대화 상자 기반 응용 프로그램 정의 따라 폼 기반입니다. 대화 상자 기반 응용 프로그램 만들기 및 액세스 방법 폼을 사용자 고유의 추가로 관리 해야 합니다 문서/뷰 아키텍처를 사용 하지 않습니다.  
  
 폼 기반 응용 프로그램에 대 한 기본 클래스는 [CFormView](../../mfc/reference/cformview-class.md)합니다. 응용 프로그램에 데이터베이스 지원을 경우에서 파생 되는 모든 클래스를 선택할 수도 `CFormView`합니다. 폼에서 파생 된 창은 `CFormView` 에서 상속 된 클래스에서 또는 `CFormView`합니다.  
  
 와 같은 기본 클래스를 사용 하는 경우에 [CView](../../mfc/reference/cview-class.md), 나중에 의해 폼 기반 응용 프로그램 만들 수 있습니다 [MFC 클래스 추가](../../mfc/reference/adding-an-mfc-class.md) 에서 파생 된 `CFormView` 및 검사는 **DocTemplate 생성 리소스** 확인란을 선택은 [MFC 클래스 마법사](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md)합니다.  
  
 마법사를 마친 후 프로젝트가 열리며, 선택한 `CFormView` (또는 클래스에서 상속 되는 `CFormView`) 기본 클래스로 Visual c + + 대화 상자 편집기를 엽니다. 대화 상자 기반 응용 프로그램을 만든 경우 또는 합니다. 이 시점에서 폼을 만들 준비가 되었습니다.  
  
### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>폼 기반 MFC 실행 파일 만들기를 시작 하려면  
  
1.  지시에 따라 [MFC 응용 프로그램을 만드는](../../mfc/reference/creating-an-mfc-application.md)합니다.  
  
2.  MFC 응용 프로그램 마법사에서 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 선택 페이지는 **문서/뷰 아키텍처 지원** 확인란 합니다.  
  
3.  선택 **단일 문서**, **여러 문서**, 또는 **다중 최상위 문서**합니다.  
  
    > [!NOTE]
    >  기본적으로 SDI, MDI 또는 다중 최상위 문서 인터페이스 응용 프로그램을 선택한 경우 `CView` 의 응용 프로그램의 뷰에 대 한 기본 클래스로 설정 됩니다는 [생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 마법사의 페이지입니다. 폼 기반 응용 프로그램을 만들려면 선택 해야 `CFormView` 응용 프로그램의 뷰에 대 한 기본 클래스로 합니다. 마법사 폼 기반 응용 프로그램에 대 한 없는 인쇄 지원을 제공 하는지 확인 합니다.  
  
4.  마법사의 다른 페이지에 원하는 프로젝트 옵션을 설정 합니다.  
  
5.  클릭 **마침** 기본 응용 프로그램을 생성 합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [파생 된 뷰 클래스](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [문서/뷰 아키텍처의 대체](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [응용 프로그램 디자인 선택](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [폼 보기](../../mfc/form-views-mfc.md)   
 [파일 탐색기 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [웹 브라우저 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

