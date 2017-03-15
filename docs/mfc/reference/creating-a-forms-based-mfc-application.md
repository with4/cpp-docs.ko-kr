---
title: "폼 기반 MFC 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcforms.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램[MFC], 폼 기반"
  - "폼 기반 응용 프로그램"
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 폼 기반 MFC 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

폼은 사용자가 데이터에 액세스하여 데이터를 변경할 수 있도록 하는 컨트롤이 포함된 대화 상자입니다.  사용자가 폼의 선택 항목에서 선택할 수 있는 응용 프로그램을 개발할 수 있습니다.  일반적으로 폼 기반 응용 프로그램에서 사용자는 **파일** 메뉴의 **새로 만들기** 를 클릭하여 폼에 액세스할 수 있습니다.  그러나 사용자가 **파일** 메뉴의 **새로 만들기** 옵션에 액세스할 수 없는 대화 상자 기반 응용 프로그램도 폼 기반 응용 프로그램으로 간주됩니다.  
  
 SDI\(Single Document Interface\) 폼 기반 응용 프로그램에서는 특정 폼의 인스턴스를 한 번에 하나만 실행할 수 있습니다.  **파일** 메뉴의 **새로 만들기** 옵션에서 새 폼을 선택하면 SDI 폼 기반 응용 프로그램에서 여러 폼을 동시에 실행할 수도 있습니다.  
  
 MDI\(Multiple Document Interface\) 폼 기반 응용 프로그램에서는 동일한 폼의 여러 인스턴스를 실행할 수 있습니다.  
  
 다중 최상위 문서를 지원하는 응용 프로그램을 만들 경우에는 데스크톱이 문서의 암시적 부모가 되고 문서의 프레임은 응용 프로그램의 클라이언트 영역에 제한되지 않습니다.  각각 고유의 프레임, 메뉴 및 작업 표시줄 아이콘을 갖는 문서의 여러 인스턴스를 열 수 있습니다.  문서의 여러 인스턴스를 개별적으로 닫을 수도 있지만, 첫 인스턴스의 **File** 메뉴에서 `Exit` 옵션을 선택하면 응용 프로그램의 인스턴스가 모두 닫힙니다.  
  
 SDI, MDI 및 다중 최상위 문서 응용 프로그램은 모두 폼을 기반으로 하며 문서\/뷰 아키텍처를 사용합니다.  
  
 모든 대화 상자 기반 응용 프로그램은 폼 기반으로 정의되어 있습니다.  대화 상자 기반 응용 프로그램에서는 문서\/뷰 아키텍처를 사용하지 않으므로 사용자 고유의 폼을 추가로 만들 경우에는 만들기 작업과 액세스 방법을 직접 관리해야 합니다.  
  
 폼 기반 응용 프로그램의 기본 클래스는 [CFormView](../../mfc/reference/cformview-class.md)입니다.  사용하고 있는 응용 프로그램에서 데이터베이스를 지원할 경우에는 `CFormView`에서 파생된 클래스도 모두 선택할 수 있습니다.  폼은 `CFormView` 또는 `CFormView`에서 상속된 클래스에서 파생된 창입니다.  
  
 [CView](../../mfc/reference/cview-class.md)와 같은 기본 클래스를 사용하더라도, `CFormView`에서 파생된 [MFC 클래스 추가](../../mfc/reference/adding-an-mfc-class.md) 및 [MFC 클래스 마법사](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md)의 **DodTemplate 리소스 생성** 확인란 선택을 통해 나중에 폼 기반 응용 프로그램을 만들 수 있습니다.  
  
 마법사를 마치면 프로젝트가 열리며, `CFormView`\(또는 `CFormView`에서 상속된 클래스\)를 기본 클래스로 선택하거나 대화 상자 기반 응용 프로그램을 만든 경우 Visual C\+\+ 에서 대화 상자 편집기를 엽니다.  이제 폼을 만들 준비가 되었습니다.  
  
### 폼 기반 MFC 실행 파일을 만들려면  
  
1.  [MFC 응용 프로그램 만들기](../../mfc/reference/creating-an-mfc-application.md)의 지시를 따릅니다.  
  
2.  MFC 응용 프로그램 마법사의[응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서\/뷰 아키텍처 지원** 확인란을 선택합니다.  
  
3.  **단일 문서**, **다중 문서** 또는 **다중 최상위 문서**를 선택합니다.  
  
    > [!NOTE]
    >  SDI, MDI 또는 다중 최상위 문서 인터페이스 응용 프로그램을 선택한 경우, 마법사의 [생성된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지에서 응용 프로그램의 뷰에 대한 기본 클래스로 `CView`가 기본 설정됩니다.  폼 기반 응용 프로그램을 만들려면 응용 프로그램의 뷰에 대한 기본 클래스로 `CFormView`를 선택해야 합니다.  마법사에서는 폼 기반 응용 프로그램에 대한 인쇄 지원은 제공하지 않습니다.  
  
4.  마법사의 나머지 페이지에서 원하는 기타 프로젝트 옵션을 설정합니다.  
  
5.  **마침**을 클릭하여 기초 응용 프로그램을 생성합니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [파생 뷰 클래스](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [문서\/뷰 아키텍처의 대체](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [응용 프로그램 디자인 선택](../../mfc/application-design-choices.md)  
  
## 참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [폼 뷰](../../mfc/form-views-mfc.md)   
 [파일 탐색기 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [웹 브라우저 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)