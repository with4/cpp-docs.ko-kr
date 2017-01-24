---
title: "MFC 응용 프로그램 마법사, 응용 프로그램 종류 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.apptype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "정적 라이브러리, MFC"
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 응용 프로그램 마법사, 응용 프로그램 종류
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)의 이 페이지를 사용하여 새 MFC 응용 프로그램을 디자인하고 기본적인 기능을 추가합니다.  
  
 **응용 프로그램 종류**  
 응용 프로그램에서 만들려는 문서 지원 형식을 지정합니다.  선택하는 응용 프로그램 종류에 따라 응용 프로그램에서 사용할 수 있는 사용자 인터페이스 옵션이 결정됩니다.  자세한 내용은 [MFC 응용 프로그램 마법사, 사용자 인터페이스 기능](../../mfc/reference/user-interface-features-mfc-application-wizard.md)를 참조하십시오.  
  
 문서 형식에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [SDI 및 MDI](../../mfc/sdi-and-mdi.md)  
  
-   [프레임 창](../../mfc/frame-windows.md)  
  
-   [프레임 창 클래스](../../mfc/frame-window-classes.md)  
  
-   [문서, 뷰 및 프레임워크](../../mfc/documents-views-and-the-framework.md)  
  
-   [대화 상자](../../mfc/dialog-boxes.md)  
  
|옵션|설명|  
|--------|--------|  
|**단일 문서**|뷰 클래스가 [CView Class](../../mfc/reference/cview-class.md)를 기반으로 하는 응용 프로그램에 대한 SDI\(단일 문서 인터페이스\) 아키텍처를 만듭니다.  마법사의 [MFC 응용 프로그램 마법사, 생성된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지에서 뷰의 기본 클래스를 변경할 수 있습니다.  예를 들어, 폼 기반 응용 프로그램을 만들려면 뷰 클래스에 [CFormView Class](../../mfc/reference/cformview-class.md)를 사용합니다.<br /><br /> 이 응용 프로그램 종류에서 문서의 프레임 창은 문서를 한 개만 포함할 수 있습니다.|  
|**다중 문서**|뷰 클래스가 `CView`를 기반으로 하는 응용 프로그램에 대한 MDI\(다중 문서 인터페이스\) 아키텍처를 만듭니다.  마법사의 **생성된 클래스** 페이지에서 뷰의 기본 클래스를 변경할 수 있습니다.  예를 들어, 폼 기반 응용 프로그램을 만들려면 뷰 클래스에 `CFormView`를 사용합니다.<br /><br /> 이 응용 프로그램 종류에서 문서의 프레임 창은 여러 개의 자식 창을 포함할 수 있습니다.|  
|**탭 문서**|각 문서를 별도의 탭에 배치합니다.|  
|**대화 상자 기반**|대화 상자 클래스가 `CDialog`를 기반으로 하는 응용 프로그램에 대한 대화 상자 기반 아키텍처를 만듭니다. HTML 대화 상자를 만들려면 **\[HTML\] 대화 상자 사용**을 선택합니다.|  
|**HTML 대화 상자 사용\(I\)**|대화 상자 기반 응용 프로그램에서만 사용할 수 있습니다.  [CDialog Class](../../mfc/reference/cdialog-class.md) 대신 [CDHtmlDialog Class](../../mfc/reference/cdhtmldialog-class.md)에서 대화 상자 클래스를 파생시킵니다.  이 확인란을 선택하면 마법사의 [MFC 응용 프로그램 마법사, 생성된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지에서 **기본 클래스** 상자에 `CDHtmlDialog`가 표시됩니다.<br /><br /> `CDHtmlDialog`에서 파생된 대화 상자에서는 HTML 기반 대화 상자를 표시하며 HTML 컨트롤을 사용하여 데이터를 교환하고 HTML 이벤트를 처리합니다.|  
|**다중 최상위 문서\(T\)**|뷰 클래스가 `CView`를 기반으로 하는 응용 프로그램에 대한 다중 최상위 아키텍처를 만듭니다.<br /><br /> 이 응용 프로그램 종류에서는 사용자가 **파일** 메뉴에서 **새로 만들기** 또는 **새 프레임**을 클릭하면 데스크톱이 암시적 부모가 되는 창이 만들어집니다.  새 문서 프레임은 작업 표시줄에 표시되고 응용 프로그램 창의 클라이언트 영역에 제한되지 않습니다.|  
  
 **문서\/뷰 아키텍처 지원**  
 [CDocument Class](../../mfc/reference/cdocument-class.md) 및 [CView Class](../../mfc/reference/cview-class.md)를 사용하여 응용 프로그램에 문서\/뷰 아키텍처를 포함할지 여부를 지정합니다\(기본값\).  MFC가 아닌 응용 프로그램을 이식하거나 컴파일된 실행 파일의 크기를 줄이려는 경우에는 이 확인란의 선택을 취소하십시오.  기본적으로 문서\/뷰 아키텍처가 없는 응용 프로그램은 [CWinApp Class](../../mfc/reference/cwinapp-class.md)에서 파생되며 이러한 응용 프로그램에는 디스크 파일에서 문서를 열 수 있도록 하는 MFC 지원 기능이 없습니다.  
  
 **리소스 언어**  
 리소스의 언어를 설정합니다.  Visual Studio에 의해 설치된 언어 중 시스템에서 사용할 수 있는 언어 목록이 표시됩니다.  시스템 언어 외의 언어를 선택하려면 해당 언어에 대한 템플릿 폴더가 이미 설치되어 있어야 합니다.  **리소스 언어** 목록에 있는 기본 언어 이외의 언어 리소스 설치에 대한 자세한 내용은 [다른 언어에 대한 마법사 지원](../../ide/wizard-support-for-other-languages.md)을 참조하십시오.  
  
 선택한 언어는 마법사의 [MFC 응용 프로그램 마법사, 문서 템플릿 문자열](../../mfc/reference/document-template-strings-mfc-application-wizard.md) 페이지에서 **지역화된 문자열** 옵션에 반영됩니다.  
  
 **유니코드 라이브러리 사용**  
 MFC 라이브러리의 유니코드 버전을 사용할 것인지 비유니코드 버전을 사용할 것인지를 지정합니다.  
  
 **프로젝트 스타일**  
 Indicates whether your application has a standard MFC, File Explorer, Visual Studio, or Office architecture and display.  자세한 내용은 [파일 탐색기 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)을 참조하십시오.  
  
|옵션|설명|  
|--------|--------|  
|**MFC 표준**|표준 MFC 응용 프로그램 아키텍처를 제공합니다.|  
|**파일 탐색기**|Implements a File Explorer–like application by using a splitter window where the left pane is a [CTreeView Class](../../mfc/reference/ctreeview-class.md) and the right pane is a [CListView Class](../../mfc/reference/clistview-class.md).|  
|**Visual Studio**|[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)에서 파생된 **파일 뷰**, **클래스 뷰**, **속성** 및 **출력**의 네 가지 도킹 가능한 창과 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)에서 파생된 주 프레임 창을 포함하는 Visual Studio 방식 응용 프로그램을 구현합니다\(기본값\).|  
|**Office**|[CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)에서 파생된 리본, [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)에서 파생된 Outlook 표시줄, [CMFCCaptionBar 클래스](../../mfc/reference/cmfccaptionbar-class.md)에서 파생된 캡션 표시줄 및 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)에서 파생된 주 프레임을 포함하는 Office 방식 응용 프로그램을 구현합니다.|  
  
 **비주얼 스타일 및 색**  
 응용 프로그램의 비주얼 스타일을 결정합니다.  사용할 수 있는 옵션은 다음과 같습니다.  
  
-   **Windows 원형\/기본**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007\(파랑 테마\)**  
  
-   **Office 2007\(검정 테마\)**  
  
-   **Office 2007\(은색 테마\)**  
  
-   **Office 2007\(바다색 테마\)**  
  
 **비주얼 스타일 전환 사용**  
 사용자가 런타임에 응용 프로그램의 비주얼 스타일을 변경할 수 있는지 여부를 지정합니다. 대개 메뉴나 리본에서 원하는 비주얼 스타일을 선택하여 변경합니다.  
  
 **MFC 사용**  
 MFC 라이브러리에 연결하는 방법을 지정합니다.  기본적으로 MFC는 공유 DLL로 연결됩니다.  
  
|옵션|설명|  
|--------|--------|  
|**공유 DLL 사용**|MFC 라이브러리를 공유 DLL로 응용 프로그램에 연결합니다.  응용 프로그램에서는 런타임에 MFC 라이브러리를 호출합니다.  이 옵션을 사용하면 MFC 라이브러리를 사용하는 여러 개의 실행 파일로 구성된 응용 프로그램의 디스크 및 메모리 요구 사항이 줄어듭니다.  Win32 및 MFC 응용 프로그램 모두 DLL에서 함수를 호출할 수 있습니다\(기본값\).|  
|**정적 라이브러리에서 MFC 사용\(E\)**|빌드할 때 응용 프로그램을 정적 MFC 라이브러리에 연결합니다.|  
  
## 참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)