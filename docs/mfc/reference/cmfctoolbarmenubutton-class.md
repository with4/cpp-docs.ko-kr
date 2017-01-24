---
title: "CMFCToolBarMenuButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarMenuButton class"
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

팝업 메뉴를 포함 하는 도구 모음 단추  
  
## 구문  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](../Topic/CMFCToolBarMenuButton::CMFCToolBarMenuButton.md)|`CMFCToolBarMenuButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarMenuButton::CompareWith](../Topic/CMFCToolBarMenuButton::CompareWith.md)|이 인스턴스와 제공 된 비교 `CMFCToolBarButton` 개체입니다.  \(재정의 [CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md).\)|  
|[CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md)|현재 단추를 다른 도구 모음 단추의 속성을 복사합니다.  \(재정의 [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|[CMFCToolBarMenuButton::CreateFromMenu](../Topic/CMFCToolBarMenuButton::CreateFromMenu.md)|도구 모음 메뉴에서 Windows 메뉴 핸들을 초기화합니다.|  
|[CMFCToolBarMenuButton::CreateMenu](../Topic/CMFCToolBarMenuButton::CreateMenu.md)|구성 도구 모음 메뉴에서 명령 중 Windows 메뉴를 만듭니다.  창 메뉴에는 핸들을 반환합니다.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md)|팝업 메뉴 개체를 만듭니다 \([CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\) 도구 모음 메뉴를 표시 합니다.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](../Topic/CMFCToolBarMenuButton::EnableQuickCustomize.md)||  
|[CMFCToolBarMenuButton::GetCommands](../Topic/CMFCToolBarMenuButton::GetCommands.md)|도구 모음 메뉴에서 명령 목록에 읽기 전용 액세스를 제공합니다.|  
|[CMFCToolBarMenuButton::GetImageRect](../Topic/CMFCToolBarMenuButton::GetImageRect.md)|단추 이미지에 대 한 경계 사각형을 검색합니다.|  
|[CMFCToolBarMenuButton::GetPaletteRows](../Topic/CMFCToolBarMenuButton::GetPaletteRows.md)|메뉴 팔레트 모드일 때는 팝업 메뉴에서 행 개수를 반환 합니다.|  
|[CMFCToolBarMenuButton::GetPopupMenu](../Topic/CMFCToolBarMenuButton::GetPopupMenu.md)|단추와 연결 된 팝업 메뉴 개체에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarMenuButton::HasButton](../Topic/CMFCToolBarMenuButton::HasButton.md)||  
|[CMFCToolBarMenuButton::HaveHotBorder](../Topic/CMFCToolBarMenuButton::HaveHotBorder.md)|사용자가 단추를 선택할 때 테두리 단추를 표시할지 여부를 결정 합니다.  \(재정의 [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarMenuButton::IsBorder](../Topic/CMFCToolBarMenuButton::IsBorder.md)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](../Topic/CMFCToolBarMenuButton::IsClickedOnMenu.md)||  
|[CMFCToolBarMenuButton::IsDroppedDown](../Topic/CMFCToolBarMenuButton::IsDroppedDown.md)|팝업 메뉴를 표시할지 여부를 결정 합니다.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md)|사용자가 하위 메뉴에서 선택한 메뉴 항목을 열 수 있는지 여부를 결정 하는 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarMenuButton::IsExclusive](../Topic/CMFCToolBarMenuButton::IsExclusive.md)|단추는 단독 사용 모드로, 여부도 사용자가 도구 모음 또는 단추 위로 포인터를 이동할 때 팝업 메뉴 열기를 유지 되는지 확인 합니다.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](../Topic/CMFCToolBarMenuButton::IsMenuPaletteMode.md)|팝업 메뉴에서 색상표 모드 인지 여부를 결정 합니다.|  
|[CMFCToolBarMenuButton::IsQuickMode](../Topic/CMFCToolBarMenuButton::IsQuickMode.md)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](../Topic/CMFCToolBarMenuButton::IsTearOffMenu.md)|분리 된 막대 팝업 메뉴 있는지 확인 합니다.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](../Topic/CMFCToolBarMenuButton::OnAfterCreatePopupMenu.md)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](../Topic/CMFCToolBarMenuButton::OnBeforeDrag.md)|단추를 끌 수 있는지 여부를 지정 합니다.  \(재정의 [CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md).\)|  
|[CMFCToolBarMenuButton::OnCalculateSize](../Topic/CMFCToolBarMenuButton::OnCalculateSize.md)|지정 된 디바이스 컨텍스트 및 도킹 상태 단추의 크기를 계산 하는 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarMenuButton::OnCancelMode](../Topic/CMFCToolBarMenuButton::OnCancelMode.md)|처리 하는 프레임 워크에서 호출을  [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) 메시지.  \(재정의 [CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md).\)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](../Topic/CMFCToolBarMenuButton::OnChangeParentWnd.md)|새 도구 모음에 단추를 삽입 하면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarMenuButton::OnClick](../Topic/CMFCToolBarMenuButton::OnClick.md)|마우스 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](../Topic/CMFCToolBarMenuButton::OnClickMenuItem.md)|팝업 메뉴에서 항목을 선택 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarMenuButton::OnContextHelp](../Topic/CMFCToolBarMenuButton::OnContextHelp.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 `WM_HELPHITTEST` 메시지.  \(재정의 [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md).\)|  
|[CMFCToolBarMenuButton::OnDraw](../Topic/CMFCToolBarMenuButton::OnDraw.md)|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리려면 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarMenuButton::OnDrawOnCustomizeList.md)|단추를 그리려면 프레임 워크에 의해 호출의  **명령** 창에  **사용자 지정** 대화 상자.  \(재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](../Topic/CMFCToolBarMenuButton::OpenPopupMenu.md)|팝업 메뉴를 열면 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](../Topic/CMFCToolBarMenuButton::ResetImageToDefault.md)|기본값 단추와 연결 된 이미지를 설정 합니다.  \(재정의 [CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md).\)|  
|[CMFCToolBarMenuButton::SaveBarState](../Topic/CMFCToolBarMenuButton::SaveBarState.md)|도구 모음 단추의 상태를 저장합니다.  \(재정의 [CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md).\)|  
|[CMFCToolBarMenuButton::Serialize](../Topic/CMFCToolBarMenuButton::Serialize.md)|이 개체는 보관 파일에서 읽거나 아카이브 수를 씁니다.  \(재정의 [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|[CMFCToolBarMenuButton::SetACCData](../Topic/CMFCToolBarMenuButton::SetACCData.md)|제공 된 채웁니다 `CAccessibilityData` 내게 필요한 옵션 도구 모음 단추에서 데이터로 개체입니다.  \(재정의 [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md).\)|  
|[CMFCToolBarMenuButton::SetMenuOnly](../Topic/CMFCToolBarMenuButton::SetMenuOnly.md)|단추 도구 모음에 추가할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](../Topic/CMFCToolBarMenuButton::SetMenuPaletteMode.md)|팝업 메뉴에서 색상표 모드 인지 여부를 지정 합니다.|  
|[CMFCToolBarMenuButton::SetMessageWnd](../Topic/CMFCToolBarMenuButton::SetMessageWnd.md)||  
|[CMFCToolBarMenuButton::SetRadio](../Topic/CMFCToolBarMenuButton::SetRadio.md)|메뉴 도구 모음 단추를 선택 되어 있는지를 나타내는 아이콘이 표시 됩니다.|  
|[CMFCToolBarMenuButton::SetTearOff](../Topic/CMFCToolBarMenuButton::SetTearOff.md)|지정 된 분리 ID에 대 한 팝업 메뉴 막대 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](../Topic/CMFCToolBarMenuButton::DrawDocumentIcon.md)|아이콘에서 메뉴 단추를 그립니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarMenuButton::m\_bAlwaysCallOwnerDraw](../Topic/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw.md)|경우 `TRUE`, 프레임 워크는 항상 호출 [CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md) 단추 때 그려집니다.|  
  
## 설명  
 A `CMFCToolBarMenuButton` 메뉴, 하위 메뉴가 있는 메뉴 항목, 명령을 실행 하거나 메뉴를 표시 하는 단추 또는 메뉴에만 표시 하는 단추를 표시할 수 있습니다.  이미지, 텍스트, 메뉴 핸들 매개 변수를 지정 하 여 메뉴 버튼의 모양과 동작을 결정 하 고 명령 단추에는 생성자와 관련 된 ID `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 사용자 지정 클래스에서 파생 된 `CMFCToolbarMenuButton` 클래스를 사용 해야는 [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) 매크로.  [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) 매크로 응용 프로그램을 닫을 때 오류를 생성 합니다.  
  
## 예제  
 다음 예제에서는 구성 된 `CMFCToolBarMenuButton` 개체.  드롭다운 메뉴에서 색상표 모드를 지정 하 고 사용자 메뉴 모음에서 메뉴 단추를 끌 때 만들어지는 분리 막대의 ID를 지정 하는 코드를 보여 줍니다.  이 코드 조각에 속해 있는  [워드 패드 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#10](../../mfc/reference/codesnippet/CPP/cmfctoolbarmenubutton-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbarmenubutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)