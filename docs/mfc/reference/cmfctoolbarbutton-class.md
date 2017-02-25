---
title: "CMFCToolBarButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarButton class"
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCToolBarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

도구 모음 단추 기능을 제공합니다.  
  
## 구문  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarButton::CMFCToolBarButton](../Topic/CMFCToolBarButton::CMFCToolBarButton.md)|생성 및 초기화는 `CMFCToolBarButton` 개체입니다.|  
|`CMFCToolBarButton::~CMFCToolBarButton`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarButton::CanBeDropped](../Topic/CMFCToolBarButton::CanBeDropped.md)|사용자 중 사용자 지정 도구 모음 또는 메뉴에 단추를 배치할 수 있습니다 여부를 지정 합니다.|  
|[CMFCToolBarButton::CanBeStored](../Topic/CMFCToolBarButton::CanBeStored.md)|단추를 저장할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md)|사용자 중 사용자 지정 단추를 늘릴 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md)|이 인스턴스와 제공 된 비교 `CMFCToolBarButton` 개체입니다.|  
|[CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)|현재 단추를 다른 도구 모음 단추의 속성을 복사합니다.|  
|[CMFCToolBarButton::CreateFromOleData](../Topic/CMFCToolBarButton::CreateFromOleData.md)|생성 된 `CMFCToolBarButton` 개체에서 제공 된 `COleDataObject` 개체.|  
|`CMFCToolBarButton::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCToolBarButton::EnableWindow](../Topic/CMFCToolBarButton::EnableWindow.md)|마우스 및 키보드 입력을 사용할 수 있거나.|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|텍스트 도구 모음 단추에서는 메뉴에 복사 합니다.|  
|[CMFCToolBarButton::GetClipboardFormat](../Topic/CMFCToolBarButton::GetClipboardFormat.md)|응용 프로그램에 대 한 전역 클립보드 형식을 검색합니다.|  
|[CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다.|  
|[CMFCToolBarButton::GetImage](../Topic/CMFCToolBarButton::GetImage.md)|단추의 이미지 인덱스를 검색합니다.|  
|[CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md)|영역을 그려야 단추의 클라이언트 영역을 검색 합니다.|  
|[CMFCToolBarButton::GetParentWnd](../Topic/CMFCToolBarButton::GetParentWnd.md)|단추의 부모 창을 검색합니다.|  
|[CMFCToolBarButton::GetProtectedCommands](../Topic/CMFCToolBarButton::GetProtectedCommands.md)|사용자가 사용자 지정할 수 없는 명령의 목록을 검색 합니다.|  
|[CMFCToolBarButton::GetTextSize](../Topic/CMFCToolBarButton::GetTextSize.md)|단추 텍스트의 크기를 검색합니다.|  
|[CMFCToolBarButton::HasFocus](../Topic/CMFCToolBarButton::HasFocus.md)|단추에 현재 입력된 포커스가 있는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md)|사용자가 단추를 선택할 때 테두리 단추를 표시할지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsDrawImage](../Topic/CMFCToolBarButton::IsDrawImage.md)|이미지 단추를 표시할지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsDrawText](../Topic/CMFCToolBarButton::IsDrawText.md)|텍스트 레이블 단추를 표시할지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsDroppedDown](../Topic/CMFCToolBarButton::IsDroppedDown.md)|단추 하위 메뉴를 표시할지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsEditable](../Topic/CMFCToolBarButton::IsEditable.md)|단추를 사용자 지정할 수 있는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md)|단추는 확장된 된 테두리가 표시 될 수 있는지를 결정 합니다.|  
|[CMFCToolBarButton::IsFirstInGroup](../Topic/CMFCToolBarButton::IsFirstInGroup.md)|단추 단추 그룹의 첫 번째 위치에 있는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsHidden](../Topic/CMFCToolBarButton::IsHidden.md)|단추를 숨길지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsHorizontal](../Topic/CMFCToolBarButton::IsHorizontal.md)|가로 도구 모음에는 단추 위치 하는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsLastInGroup](../Topic/CMFCToolBarButton::IsLastInGroup.md)|단추 단추 그룹의 마지막 위치에 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::IsLocked](../Topic/CMFCToolBarButton::IsLocked.md)|잠긴된 사용자 지정 \(비\-가능한\) 도구 모음에서 단추 인지 확인 합니다.|  
|[CMFCToolBarButton::IsOwnerOf](../Topic/CMFCToolBarButton::IsOwnerOf.md)|단추에 제공 된 창 핸들의 소유자 인지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsVisible](../Topic/CMFCToolBarButton::IsVisible.md)|도구 모음 단추가 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsWindowVisible](../Topic/CMFCToolBarButton::IsWindowVisible.md)|단추의 내부 창 핸들이 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)|단추를 처리 하는지 여부를 지정 하는  [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지.|  
|[CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md)|단추를 추가 하면 프레임 워크에서 호출을  **사용자 지정** 대화 상자.|  
|[CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md)|단추를 끌 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::OnBeforeDrop](../Topic/CMFCToolBarButton::OnBeforeDrop.md)|사용자가 대상 도구 모음 단추를 삭제할 수 있습니다 여부를 지정 합니다.|  
|[CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)|지정 된 디바이스 컨텍스트 및 도킹 상태 단추의 크기를 계산 하는 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md)|처리 하는 프레임 워크에서 호출을  [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) 메시지.|  
|[CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)|새 도구 모음에 단추를 삽입 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)|마우스 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md)|마우스 단추를 놓을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 `WM_HELPHITTEST` 메시지.|  
|[CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 `WM_CTLCOLOR` 메시지.|  
|[CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md)|단추를 응용 프로그램 상위 도구 모음에 바로 가기 메뉴를 표시할 때 제공 된 메뉴를 수정할 수 있습니다.|  
|[CMFCToolBarButton::OnDblClk](../Topic/CMFCToolBarButton::OnDblClk.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) 메시지.|  
|[CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리려면 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)|단추를 그리려면 프레임 워크에 의해 호출의  **명령** 창에  **사용자 지정** 대화 상자.|  
|[CMFCToolBarButton::OnGetCustomToolTipText](../Topic/CMFCToolBarButton::OnGetCustomToolTipText.md)|단추에 대 한 사용자 지정 도구 설명 텍스트를 검색 하는 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md)|전체 글꼴을 변경할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md)|상위 도구 모음을 이동 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md)|단추 될 때 프레임 워크에서 보이거나 보이지 않는 호출 됩니다.|  
|[CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md)|프레임 워크에서 상위 도구 모음 크기를 변경 하거나 위치 및이 변경 단추 크기를 변경 하려면 필요한 경우 호출 됩니다.|  
|[CMFCToolBarButton::OnToolHitTest](../Topic/CMFCToolBarButton::OnToolHitTest.md)|상위 도구 모음 단추의 경계 사각형의 점은 여부를 결정 해야 할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md)|상위 도구 모음 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarButton::PrepareDrag](../Topic/CMFCToolBarButton::PrepareDrag.md)|단추 끌어서 놓기 작업을 수행 하려고 할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::Rect](../Topic/CMFCToolBarButton::Rect.md)|단추의 경계 사각형을 검색합니다.|  
|[CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md)|기본값 단추와 연결 된 이미지를 설정 합니다.|  
|[CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md)|도구 모음 단추의 상태를 저장합니다.|  
|[CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)|이 개체는 보관 파일에서 읽거나 아카이브 수를 씁니다.  \(재정의 [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md)|제공 된 채웁니다 `CAccessibilityData` 내게 필요한 옵션 도구 모음 단추에서 데이터로 개체입니다.|  
|[CMFCToolBarButton::SetClipboardFormatName](../Topic/CMFCToolBarButton::SetClipboardFormatName.md)|글로벌 클립보드 형식을 이름을 바꿉니다.|  
|[CMFCToolBarButton::SetImage](../Topic/CMFCToolBarButton::SetImage.md)|단추의 이미지 인덱스를 설정합니다.|  
|[CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md)|사용자가 사용자 지정할 수 없는 명령의 목록을 설정 합니다.|  
|[CMFCToolBarButton::SetRadio](../Topic/CMFCToolBarButton::SetRadio.md)|단추는 선택 된 상태가 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::SetRect](../Topic/CMFCToolBarButton::SetRect.md)|단추의 경계 사각형을 설정합니다.|  
|[CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md)|단추의 스타일을 설정합니다.|  
|[CMFCToolBarButton::SetVisible](../Topic/CMFCToolBarButton::SetVisible.md)|단추를 표시할지 여부를 지정 합니다.|  
|[CMFCToolBarButton::Show](../Topic/CMFCToolBarButton::Show.md)|표시 하거나 단추를 숨깁니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarButton::m\_bImage](../Topic/CMFCToolBarButton::m_bImage.md)|단추에 이미지를 표시할지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_bText](../Topic/CMFCToolBarButton::m_bText.md)|텍스트 레이블 단추를 표시할지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_bTextBelow](../Topic/CMFCToolBarButton::m_bTextBelow.md)|아래 이미지는 단추에 텍스트 레이블을 표시할지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_bUserButton](../Topic/CMFCToolBarButton::m_bUserButton.md)|단추를 사용자 정의 이미지를 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_bWholeText](../Topic/CMFCToolBarButton::m_bWholeText.md)|경계 사각형에 맞지 않는 경우에 단추 전체 텍스트 레이블이 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_bWrap](../Topic/CMFCToolBarButton::m_bWrap.md)|단추 구분선 옆에 있는 다음 행에 배치 됩니다 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_bWrapText](../Topic/CMFCToolBarButton::m_bWrapText.md)|여러 줄 텍스트 레이블을 사용할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m\_nID](../Topic/CMFCToolBarButton::m_nID.md)|단추 명령 ID입니다.|  
|[CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md)|단추의 스타일입니다.|  
|[CMFCToolBarButton::m\_strText](../Topic/CMFCToolBarButton::m_strText.md)|단추 텍스트 레이블입니다.|  
  
## 설명  
 A `CMFCToolbarButton` 개체 도구 모음에 있는 컨트롤입니다.  동작 하는 일반적인 단추와 비슷합니다.  이 개체에는 이미지와 텍스트 레이블을 할당할 수 있습니다.  도구 모음 단추 명령 ID도 있습니다.  도구 모음 단추를 클릭할 때 프레임 워크는이 ID를 지정 하는 명령을 실행 합니다.  
  
 일반적으로 도구 모음 단추 사용자 지정할 수 있습니다: 사용자 수 도구 모음에서 다른 단추를 끌어 및 복사, 붙여넣기, 삭제 및 텍스트 레이블, 이미지 편집.  도구 모음 사용자 지정에서 사용자를 방지 하려면 다음 두 가지 도구 모음을 잠글 수 있습니다.  설정의 `bLocked` 플래그 `TRUE` 호출 하면 [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md), 또는 사용 하 여 보호 된 명령의 전체 목록에는 개별 단추의 명령 ID 추가 [CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md) 메서드.  
  
 `CMFCToolBarButton`응용 프로그램에서 전역 컬렉션의 이미지를 도구 모음에서 이미지를 표시 하는 개체입니다.  이러한 컬렉션의 상위 도구 모음에서 유지 되는 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  자세한 내용은 [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md)를 참조하십시오.  
  
 도구 모음 단추를 클릭할 때 부모 도구 모음의 마우스 메시지를 처리 하 고 전달 단추에 적절 한 작업.  유효한 명령 ID는 단추가 있는 경우 상위 도구 모음에 전송 된 `WM_COMMAND` 메시지를 부모 프레임.  
  
 `CMFCToolBarButton` 클래스는 다른 도구 모음 단추 클래스의 기본 클래스 같은 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md), [CMFCToolBarEditBoxButton Class](../../mfc/reference/cmfctoolbareditboxbutton-class.md), 및 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
## 예제  
 구성 하는 방법 다음 예제는 `CMFCToolBarButton` 의 다양 한 메서드를 사용 하 여 개체의 `CMFCToolBarButton` 클래스.  마우스를 사용 하 고 키보드 입력, 단추의 이미지 인덱스를 설정할 경계 사각형 단추를 설정 하 고 단추를 표시 하는 방법의 예제입니다.  이 코드 조각에 속해 있는  [탭 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TabControl#1](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_TabControl#2](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbarbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md)   
 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)   
 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)