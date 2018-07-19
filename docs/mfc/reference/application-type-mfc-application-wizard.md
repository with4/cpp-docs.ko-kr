---
title: MFC 응용 프로그램 마법사, 응용 프로그램 종류 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.apptype
dev_langs:
- C++
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5708e823c57ecdb8470a398c4192cba1a5b6e411
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353441"
---
# <a name="application-type-mfc-application-wizard"></a>MFC 응용 프로그램 마법사, 응용 프로그램 종류
이 페이지는 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md) 디자인 하 고 새 MFC 응용 프로그램에 기본 기능을 추가 합니다.  
  
 **응용 프로그램 종류**  
 응용 프로그램에서 만들려는 지원 문서 유형을 지정 합니다. 선택한 응용 프로그램 종류는 응용 프로그램에 사용할 수 있는 사용자 인터페이스 옵션을 결정 합니다. 참조 [MFC 응용 프로그램 마법사, 사용자 인터페이스 기능](../../mfc/reference/user-interface-features-mfc-application-wizard.md) 자세한 정보에 대 한 합니다.  
  
 문서 종류에 대 한 자세한 내용은 다음을 참조:  
  
-   [SDI 및 MDI](../../mfc/sdi-and-mdi.md)  
  
-   [프레임 창](../../mfc/frame-windows.md)  
  
-   [프레임 창 클래스](../../mfc/frame-window-classes.md)  
  
-   [문서, 뷰 및 프레임워크](../../mfc/documents-views-and-the-framework.md)  
  
-   [대화 상자](../../mfc/dialog-boxes.md)  
  
|옵션|설명|  
|------------|-----------------|  
|**단일 문서**|뷰 클래스 기반으로 응용 프로그램에 대 한 단일 문서 SDI (인터페이스)는 아키텍처가 생성 [CView 클래스](../../mfc/reference/cview-class.md)합니다. 뷰에 대 한 기본 클래스를 변경할 수는 [MFC 응용 프로그램 마법사, 생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 마법사의 페이지입니다. 폼 기반 응용 프로그램을 만들려면 사용 예를 들어 [CFormView 클래스](../../mfc/reference/cformview-class.md) 뷰 클래스에 대 한 합니다.<br /><br /> 이 유형의 응용 프로그램에는 문서 프레임 창 하나의 문서를 포함할 수 있습니다.|  
|**여러 문서**|뷰 클래스 기반으로 응용 프로그램에 대 한 다중 문서 인터페이스 (mdi 다중) 아키텍처를 만듭니다 `CView`합니다. 뷰에 대 한 기본 클래스를 변경할 수는 **생성 된 클래스** 마법사의 페이지입니다. 폼 기반 응용 프로그램을 만들려면 사용 예를 들어 `CFormView` 뷰 클래스에 대 한 합니다.<br /><br /> 이 유형의 응용 프로그램에는 문서 프레임 창 수 여러 자식 창을 포함할 합니다.|  
|**탭된 문서**|별도 탭에 각 문서를 배치합니다.|  
|**대화 상자 기반**|대화 상자 클래스 기반으로 하는 응용 프로그램에 대 한 대화 상자 기반 아키텍처를 만들고 `CDialog`합니다. (HTML 대화를 만들려면 선택 **사용**.)|  
|**HTML 사용 하 여 대화 상자**|대화 상자 응용 프로그램만 해당 합니다. 대화 상자 클래스에서 파생 [CDHtmlDialog 클래스](../../mfc/reference/cdhtmldialog-class.md) 대신 [CDialog 클래스](../../mfc/reference/cdialog-class.md)합니다. 이 상자를 선택 하는 경우 `CDHtmlDialog` 에 나열 된는 **기본 클래스** 상자에 [MFC 응용 프로그램 마법사, 생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 마법사의 페이지입니다.<br /><br /> A `CDHtmlDialog`-HTML 기반 대화 상자를 표시 하는 파생 된 대화 상자, html 데이터를 교환 제어 하 고 HTML 이벤트를 처리 합니다.|  
|**다중 최상위 문서**|뷰 클래스 기반으로 응용 프로그램에 대 한 여러 최상위 아키텍처를 만듭니다 `CView`합니다.<br /><br /> 이 유형의 응용 프로그램을 클릭할 때 **새로** (또는 **새 프레임**)에 **파일** 응용 프로그램 메뉴에서 해당 부모는 암시적으로 바탕 화면 창을 만듭니다. 새 문서 프레임 작업 표시줄에 표시 되 고 응용 프로그램 창의 클라이언트 영역에 제한 되지 않습니다.|  
  
 **문서/뷰 아키텍처 지원**  
 문서/뷰 아키텍처를 사용 하 여 응용 프로그램에 포함할지 여부를 지정 된 [CDocument 클래스](../../mfc/reference/cdocument-class.md) 및 [CView 클래스](../../mfc/reference/cview-class.md) (기본값). 컴파일된 실행 파일의 크기를 줄이는 경우 또는 비 MFC 응용 프로그램을 이식 하는 경우이 확인란의 선택을 취소 합니다. 기본적으로 문서/뷰 아키텍처 없이 응용 프로그램에서 파생 된 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md), 디스크 파일에서 문서를 열에 대 한 MFC 지원을 포함 하지 않습니다.  
  
 **리소스 언어**  
 리소스의 언어를 설정합니다. 목록으로 Visual Studio 설치 된 시스템에서 사용할 수 있는 언어를 표시 합니다. 시스템 언어 이외의 언어를 선택 하려면 해당 언어에 대 한 템플릿 폴더가 이미 설치 되어 있어야 합니다. 에 있는 기본와에서 다른 언어 리소스를 설치 하는 방법에 대 한 자세한 내용은 **리소스 언어** 목록에서 참조 [다른 언어에 대 한 마법사 지원](../../ide/wizard-support-for-other-languages.md)합니다.  
  
 선택한 언어에 반영 됩니다는 **지역화 된 문자열** 의 옵션은 [MFC 응용 프로그램 마법사, 문서 템플릿 문자열](../../mfc/reference/document-template-strings-mfc-application-wizard.md) 마법사의 페이지입니다.  
  
 **유니코드 라이브러리 사용**  
 MFC 라이브러리의 유니코드 또는 비유니코드 버전 사용 여부를 지정 합니다.  
  
 **프로젝트 스타일**  
 응용 프로그램에 표준 MFC, 파일 탐색기, Visual Studio 또는 아키텍처 및 표시 여부를 나타냅니다. 자세한 내용은 참조 [파일 탐색기 스타일 MFC 응용 프로그램을 만드는](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**MFC 표준**|표준 MFC 응용 프로그램 아키텍처를 제공합니다.|  
|**파일 탐색기**|여기서는 왼쪽된 창 분할 창을 사용 하 여 파일 탐색기와 같은 응용 프로그램을 구현 하는 [CTreeView 클래스](../../mfc/reference/ctreeview-class.md) 오른쪽 창은 [CListView 클래스](../../mfc/reference/clistview-class.md)합니다.|  
|**Visual Studio**|도킹 가능한 네 개의 창이 포함 된 Visual Studio와 유사한 응용 프로그램 구현 (**파일 보기**, **클래스 뷰**, **속성**, 및 **출력**)에서 파생 되는 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md) 에서 파생 된 주 프레임 창 및 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md) (기본값).|  
|**Office**|파생 된 리본 메뉴를 포함 하는 Office와 비슷한 응용 프로그램을 구현 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)에서 파생 된 Outlook 표시줄 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)에서 파생 된 캡션 표시줄 [CMFCCaptionBar 클래스](../../mfc/reference/cmfccaptionbar-class.md), 및에서 파생 된 주 프레임 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)합니다.|  
  
 **비주얼 스타일과 색**  
 응용 프로그램의 비주얼 스타일을 결정합니다. 다음 옵션을 사용할 수 있습니다.  
  
-   **Windows 네이티브/기본값**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 (파랑 테마)**  
  
-   **Office 2007 (검정 테마)**  
  
-   **Office 2007 (은색 테마)**  
  
-   **Office 2007 (바다색 테마)**  
  
 **비주얼 스타일 전환 사용**  
 여부 사용자를 변경할 수 런타임에 응용 프로그램의 비주얼 스타일 일반적으로 메뉴 또는 리본 메뉴에서 적절 한 시각적 스타일을 선택 하 여 지정 합니다.  
  
 **MFC 사용**  
 MFC 라이브러리에 연결 하는 방법을 지정 합니다. 기본적으로 MFC 공유 DLL로 연결 됩니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**공유 DLL에서 MFC 사용**|MFC 라이브러리를 공유 DLL로 응용 프로그램에 연결합니다. 응용 프로그램에서는 실행 시 MFC 라이브러리를 호출 합니다. 이 옵션에는 MFC 라이브러리를 사용 하는 여러 실행 파일의 구성 된 응용 프로그램의 디스크 및 메모리 요구 사항을 줄일 수 있습니다. Win32 및 MFC 응용 프로그램 모두 (기본값) DLL의 함수를 호출할 수 있습니다.|  
|**정적 라이브러리에서 MFC 사용**|빌드 시 정적 MFC 라이브러리에 응용 프로그램을 연결합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [Visual C++ 프로젝트용 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)

