---
title: "컨트롤 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.control
dev_langs: C++
helpviewer_keywords:
- static display controls [MFC]
- control classes [MFC]
- buttons, MFC control classes
- controls [MFC], MFC control classes
- controls [MFC]
- list boxes [MFC], MFC control classes
- control classes [MFC], MFC
- text, controls for input [MFC]
- user input [MFC], MFC control classes
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1bba69597425c10119af1f2c7d29afd870d8c48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="control-classes"></a>컨트롤 클래스
컨트롤 클래스에 정적 텍스트 컨트롤에서 트리 컨트롤에 이르기까지 표준 Windows 컨트롤의 다양 한 캡슐화 합니다. 또한 MFC는 비트맵 및 컨트롤 막대를 사용 하는 단추 등의 몇 가지 새로운 컨트롤을 제공 합니다.  
  
 클래스 이름이 끝날 컨트롤 "**Ctrl**" Windows 95 및 Windows NT 버전 3.51에 새로 추가 된 합니다.  
  
## <a name="static-display-controls"></a>정적 디스플레이 컨트롤  
 [CStatic](../mfc/reference/cstatic-class.md)  
 정적 디스플레이 창입니다. 정적 컨트롤 레이블, 상자의 또는 대화 상자 또는 창에 있는 다른 컨트롤을 구분 하는 데 사용 됩니다. 그래픽 이미지 대신 텍스트 또는 상자 표시할 수도 있습니다.  
  
## <a name="text-controls"></a>텍스트 컨트롤  
 [CEdit](../mfc/reference/cedit-class.md)  
 편집 가능한 텍스트 컨트롤 창입니다. 편집 컨트롤은 사용자가 텍스트 입력 하는 데 사용 됩니다.  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 IP (인터넷 프로토콜) 주소를 조작 하기 위한 입력란을 지원 합니다.  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 사용자 입력 수 있으며 텍스트를 편집 하는 컨트롤입니다. 컨트롤에 캡슐화 된 달리 `CEdit`, 서식 있는 편집 컨트롤을 지 원하는 문자 및 단락 서식 지정 및 OLE 개체입니다.  
  
## <a name="controls-that-represent-numbers"></a>숫자를 나타내는 컨트롤  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 값 또는 값 집합을 선택 하는 사용자가 이동 슬라이더를 포함 하는 컨트롤입니다.  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 화살표 단추 쌍 사용자 수를 증가 또는 감소 값을 클릭 합니다.  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 작업의 진행률을 표시 하는 오른쪽에서 왼쪽 점차 채워지는 사각형을 표시 합니다.  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 스크롤 막대 컨트롤 창입니다. 클래스 대화 상자 또는 창, 사용자는 범위 내에서 위치를 지정할 수의 컨트롤로 사용 하기 위해 스크롤 막대의 기능을 제공 합니다.  
  
## <a name="buttons"></a>단추  
 [CButton](../mfc/reference/cbutton-class.md)  
 단추 컨트롤 창입니다. 클래스는 누름 단추, 확인란 또는 대화 상자 또는 창에서 라디오 단추에 대 한 프로그래밍 인터페이스를 제공합니다.  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 캡션 텍스트 대신 비트맵 단추입니다.  
  
## <a name="lists"></a>목록  
 [CListBox](../mfc/reference/clistbox-class.md)  
 목록 상자 컨트롤 창입니다. 목록 상자에 사용자를 확인 하 고 선택할 수 있는 항목의 목록이 표시 됩니다.  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Windows 목록 상자의;의 기능을 제공 사용자를 목록 상자 내에서 파일 이름 및 문자열 리터럴, 예: 목록 상자 항목을 이동할 수 있습니다. 이 기능으로 목록 상자는 알파벳 아닌 다른 순서의 항목 목록에 대 한 유용와 같은 프로젝트의 경로 이름 또는 파일을 포함 합니다.  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 콤보 상자 컨트롤 창입니다. 콤보 상자 편집 컨트롤 및 목록 상자 이루어져 있습니다.  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 이미지 목록에 대한 지원을 제공하여 콤보 상자 컨트롤을 확장합니다.  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 사용자 수 선택 하거나 선택 취소, 각 항목 옆에 있는 확인란이 있는 항목의 목록을 표시 합니다.  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 아이콘 및 레이블 파일 탐색기의 오른쪽 창에 비슷한 방식으로 구성 된 각 항목의 컬렉션을 표시 합니다.  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 아이콘 및 레이블 파일 탐색기의 왼쪽된 창에 비슷한 방식으로 정렬의 계층적 목록을 표시 합니다.  
  
## <a name="toolbars-and-status-bars"></a>도구 모음 및 상태 표시줄  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows의 도구 모음 공용 컨트롤의 기능을 제공합니다. 대부분 MFC 사용 프로그램 [CToolBar](../mfc/reference/ctoolbar-class.md) 이 클래스는 대신 합니다.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 가로 창 일반적으로 응용 프로그램 상태 정보를 표시할 수 있는 창으로 구분 합니다. 대부분 MFC 사용 프로그램 [CStatusBar](../mfc/reference/cstatusbar-class.md) 이 클래스는 대신 합니다.  
  
## <a name="miscellaneous-controls"></a>기타 컨트롤  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 간단한 비디오 클립을 표시합니다.  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 응용 프로그램 도구의 용도 설명 하는 텍스트 한 줄을 표시 하는 작은 팝업 창입니다.  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 특정 날짜 또는 시간 값을 선택할 수 있도록 허용 하는 간단한 달력 인터페이스 컨트롤 또는 확장 된 편집 컨트롤을 지원 합니다.  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 제목 또는 열에 대 한 레이블을 표시합니다.  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 사용자가 날짜를 선택 하도록 허용 하는 간단한 달력 인터페이스 컨트롤을 지원 합니다.  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 에 사용자가 클릭, 전자 필기장의 구분선과 유사 탭이 포함 된 컨트롤입니다.  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 사용자를 작업을 신속 하 게 수행 하려면 사용자를 누를 수 있는 핫 키 조합을 만들 수 있습니다.  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 마크업 텍스트를 렌더링 하 고 포함된 된 링크를 클릭할 때 적절 한 응용 프로그램을 시작 합니다.  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 MFC 창에서 WebBrowser ActiveX 컨트롤의 기능을 제공합니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Windows 이미지 목록의 기능을 제공합니다. 이미지 목록은 목록 컨트롤 및 트리 컨트롤과 함께 사용됩니다. 이러한 컨트롤은 또한 동일한 크기의 비트맵 집합을 저장하고 아카이브하는 데 사용할 수 있습니다.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows 컨트롤과 관련 된 모든 보기에 대 한 기본 클래스입니다. 컨트롤에 따라 보기에 대 한 설명은 다음과 같습니다.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Windows 표준에 포함 된 보기 편집 컨트롤입니다.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 풍부한 Windows를 포함 하는 뷰는 컨트롤을 편집 합니다.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows 목록 컨트롤을 포함 하는 뷰.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows 트리 컨트롤을 포함 하는 뷰.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

