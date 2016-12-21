---
title: "CMFCToolBar Class | Microsoft Docs"
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
  - "CMFCToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBar class"
ms.assetid: e7679c01-fb94-44c0-98c6-3af955292fb5
caps.latest.revision: 48
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCToolBar` 클래스와 유사한 [CToolBar Class](../../mfc/reference/ctoolbar-class.md), 하지만 사용자 인터페이스 기능에 대 한 추가 지원을 제공 합니다.  이러한 플랫 도구 모음, 도구 모음 핫 이미지, 큰 아이콘, 페이저 단추, 잠금된 도구 모음, rebar 컨트롤, 이미지, 배경 이미지, 텍스트를 포함 하 고 도구 모음 탭.  `CMFCToolBar` 클래스는 기본 제공 지원을 사용자 지정 도구 모음 및 메뉴, 끌어서 놓기 도구 모음 및 메뉴, 콤보 상자 단추 사이의 편집 상자 단추, 색상 선택기 단추 롤업 합니다.  
  
## 구문  
  
```  
class CMFCToolBar : public CMFCBaseToolBar  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCToolBar::CMFCToolBar`|기본 생성자입니다.|  
|`CMFCToolBar::~CMFCToolBar`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBar::AddBasicCommand](../Topic/CMFCToolBar::AddBasicCommand.md)|메뉴 명령 사용자 메뉴를 열면 항상 표시 되는 명령 목록에 추가 합니다.|  
|[CMFCToolBar::AddCommandUsage](../Topic/CMFCToolBar::AddCommandUsage.md)|지정 된 명령과 연결 된 카운터 1 증가 합니다.|  
|[CMFCToolBar::AddToolBarForImageCollection](../Topic/CMFCToolBar::AddToolBarForImageCollection.md)|응용 프로그램에서 이미지의 컬렉션에 사용자 인터페이스 리소스에서 이미지를 추가합니다.|  
|[CMFCToolBar::AdjustLayout](../Topic/CMFCToolBar::AdjustLayout.md)|크기 및 위치 도구 모음을 다시 계산합니다.  [CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)를 재정의합니다.|  
|[CMFCToolBar::AdjustSize](../Topic/CMFCToolBar::AdjustSize.md)|도구 모음의 크기를 다시 계산합니다.|  
|[CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md)|이미지 도구 모음 단추에 텍스트 레이블을 표시할 수 있습니다 여부를 지정 합니다.|  
|[CMFCToolBar::AreTextLabels](../Topic/CMFCToolBar::AreTextLabels.md)|도구 모음에서 이미지 도구 모음 단추에 현재 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBar::AutoGrayInactiveImages](../Topic/CMFCToolBar::AutoGrayInactiveImages.md)|사용 또는 비활성 단추 이미지의 자동 생성을 사용 하지 않습니다.|  
|[CMFCToolBar::ButtonToIndex](../Topic/CMFCToolBar::ButtonToIndex.md)|지정 된 항목의 인덱스를 반환 합니다. [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) 이 도구 모음에서 개체.|  
|[CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md)|도구 모음의 가로 크기를 계산합니다.  \(재정의 [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCToolBar::CalcSize](../Topic/CMFCToolBar::CalcSize.md)|프레임 워크는 레이아웃 계산 프로세스의 일부로 호출 됩니다.  \(재정의 [CPane::CalcSize](../Topic/CPane::CalcSize.md).\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|도구 모음 및 형제 같은 창에 위치한 여부를 결정 합니다.|  
|[CMFCToolBar::CleanUpImages](../Topic/CMFCToolBar::CleanUpImages.md)|이미지 도구 모음에 할당 된 시스템 리소스를 해제 합니다.|  
|[CMFCToolBar::CleanUpLockedImages](../Topic/CMFCToolBar::CleanUpLockedImages.md)|잠긴된 도구 모음 이미지를 할당 하는 시스템 리소스를 해제 합니다.|  
|[CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md)|사용자가 도구 모음을 닫을 수 있습니다 여부를 지정 합니다.  \(재정의 [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md).\)|  
|[CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)|시스템 도구 모음을 원래 상태로 사용자 지정 후 복원할 수 여부를 결정 합니다.|  
|[CMFCToolBar::CanFocus](../Topic/CMFCToolBar::CanFocus.md)|창 포커스를 받을 수 있는지 여부를 지정 합니다.  \(재정의 [CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md).\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|도구 모음 및 형제 같은 창에 위치한 여부를 결정 합니다.|  
|[CMFCToolBar::CommandToIndex](../Topic/CMFCToolBar::CommandToIndex.md)|지정 된 명령 ID 가진 도구 모음에서 단추의 인덱스를 반환|  
|[CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)|`CMFCToolBar` 개체를 만듭니다.|  
|[CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md)|생성 된 `CMFCToolBar` 큰 아이콘 추가 스타일 옵션을 사용 하 여 개체.|  
|[CMFCToolBar::Deactivate](../Topic/CMFCToolBar::Deactivate.md)|도구 모음을 비활성화합니다.|  
|[CMFCToolBar::EnableCustomizeButton](../Topic/CMFCToolBar::EnableCustomizeButton.md)|활성화 또는 비활성화는  **단추 추가 \/ 제거**  단추는 도구 모음 끝에 나타납니다.|  
|[CMFCToolBar::EnableDocking](../Topic/CMFCToolBar::EnableDocking.md)|사용의 창 주 프레임에 도킹 합니다.  \(재정의 [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md).\)|  
|[CMFCToolBar::EnableLargeIcons](../Topic/CMFCToolBar::EnableLargeIcons.md)|도구 모음 단추를 큰 아이콘을 사용할 수 있거나.|  
|[CMFCToolBar::EnableQuickCustomization](../Topic/CMFCToolBar::EnableQuickCustomization.md)|사용자가 키를 눌러 수 있도록 빠른 사용자 지정 도구 모음을 사용 하거나의  **Alt** 키를 누른 단추를 새 위치로 끕니다.|  
|[CMFCToolBar::EnableReflections](../Topic/CMFCToolBar::EnableReflections.md)|반사 명령 사용할 수 있거나.|  
|[CMFCToolBar::EnableTextLabels](../Topic/CMFCToolBar::EnableTextLabels.md)|도구 모음에서 도구 모음 단추 이미지를 사용할 수 있거나.|  
|[CMFCToolBar::FromHandlePermanent](../Topic/CMFCToolBar::FromHandlePermanent.md)|검색에 대 한 포인터는 `CMFCToolBar` 지정 된 창 핸들을 포함 하는 개체입니다.|  
|[CMFCToolBar::GetAllButtons](../Topic/CMFCToolBar::GetAllButtons.md)|단추는 읽기 전용 목록 도구 모음을 반환합니다.|  
|[CMFCToolBar::GetAllToolbars](../Topic/CMFCToolBar::GetAllToolbars.md)|응용 프로그램에서 읽기 전용 목록을 모든 도구 모음을 반환합니다.|  
|[CMFCToolBar::GetBasicCommands](../Topic/CMFCToolBar::GetBasicCommands.md)|읽기 전용 응용 프로그램에서 정의한 기본 명령 목록을 반환 합니다.|  
|[CMFCToolBar::GetButton](../Topic/CMFCToolBar::GetButton.md)|에 대 한 포인터를 반환의 `CMFCToolBarButton` 개체는 지정 된 도구 모음 단추 인덱스를 포함 합니다.|  
|[CMFCToolBar::GetButtonInfo](../Topic/CMFCToolBar::GetButtonInfo.md)|명령 ID, 스타일 및 이미지 인덱스 단추에 지정 된 인덱스를 반환합니다.|  
|[CMFCToolBar::GetButtonSize](../Topic/CMFCToolBar::GetButtonSize.md)|도구 모음의 각 버튼의 크기를 반환합니다.|  
|[CMFCToolBar::GetButtonStyle](../Topic/CMFCToolBar::GetButtonStyle.md)|현재 스타일의 지정 된 인덱스에 있는 도구 모음 단추를 반환 합니다.|  
|[CMFCToolBar::GetButtonText](../Topic/CMFCToolBar::GetButtonText.md)|지정 된 인덱스에 있는 단추의 텍스트 레이블을 반환 합니다.|  
|[CMFCToolBar::GetColdImages](../Topic/CMFCToolBar::GetColdImages.md)|컬렉션에 응용 프로그램에서 콜드 도구 모음 단추 이미지에 대 한 포인터를 반환합니다.|  
|[CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md)|도구 모음 단추의 너비를 반환합니다.|  
|[CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md)|단추는 응용 프로그램에 있는 모든 도구 모음에서 지정 된 명령 ID의 목록을 반환 합니다.|  
|[CMFCToolBar::GetCount](../Topic/CMFCToolBar::GetCount.md)|도구 모음에서 단추 및 구분 기호를 반환합니다.|  
|[CMFCToolBar::GetCustomizeButton](../Topic/CMFCToolBar::GetCustomizeButton.md)|검색에 대 한 포인터는 `CMFCCustomizeButton` 도구 모음에 연결 된 개체입니다.|  
|[CMFCToolBar::GetDefaultImage](../Topic/CMFCToolBar::GetDefaultImage.md)|기본 이미지를 도구 모음 단추에 지정 된 명령 ID의 인덱스를 반환합니다.|  
|[CMFCToolBar::GetDisabledImages](../Topic/CMFCToolBar::GetDisabledImages.md)|컬렉션에 응용 프로그램에서 사용할 수 없는 도구 모음 단추에 사용 되는 이미지에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBar::GetDisabledMenuImages](../Topic/CMFCToolBar::GetDisabledMenuImages.md)|응용 프로그램에서 사용할 수 없는 메뉴 단추에 사용 되는 이미지의 컬렉션에 포인터를 반환 합니다.|  
|[CMFCToolBar::GetDroppedDownMenu](../Topic/CMFCToolBar::GetDroppedDownMenu.md)|해당 하위 메뉴에 현재 표시 되는 메뉴 단추 개체에 대 한 포인터를 검색 합니다.|  
|[CMFCToolBar::GetGrayDisabledButtons](../Topic/CMFCToolBar::GetGrayDisabledButtons.md)|이미지 사용 안 함된 단추를 흐리게 표시 된 버전의 일반 단추 이미지 인지 여부를 지정 하거나 사용할 수 없는 단추 이미지 컬렉션에서 찍은.|  
|[CMFCToolBar::GetHighlightedButton](../Topic/CMFCToolBar::GetHighlightedButton.md)|현재 강조 도구 모음 단추에 포인터를 반환 합니다.|  
|[CMFCToolBar::GetHotBorder](../Topic/CMFCToolBar::GetHotBorder.md)|도구 모음 단추 핫 트래킹 지 확인 합니다.|  
|[CMFCToolBar::GetHotTextColor](../Topic/CMFCToolBar::GetHotTextColor.md)|강조 표시 된 도구 모음 단추의 텍스트 색을 반환합니다.|  
|[CMFCToolBar::GetHwndLastFocus](../Topic/CMFCToolBar::GetHwndLastFocus.md)|도구 모음을 완료 하기 전에 포커스가 입력 창 핸들을 반환 합니다.|  
|[CMFCToolBar::GetIgnoreSetText](../Topic/CMFCToolBar::GetIgnoreSetText.md)|단추 레이블을 설정 하는 호출을 무시할지 여부를 지정 합니다.|  
|[CMFCToolBar::GetImageSize](../Topic/CMFCToolBar::GetImageSize.md)|현재 도구 모음 단추 이미지의 크기를 반환합니다.|  
|[CMFCToolBar::GetImages](../Topic/CMFCToolBar::GetImages.md)|포인터 기본 컬렉션에는 응용 프로그램에서 단추 이미지를 반환합니다.|  
|[CMFCToolBar::GetImagesOffset](../Topic/CMFCToolBar::GetImagesOffset.md)|이 도구 모음에 도구 모음 단추 이미지의 전체 목록에 대 한 도구 모음 단추 이미지를 찾는 데 사용 하는 인덱스 오프셋을 반환 합니다.|  
|[CMFCToolBar::GetInvalidateItemRect](../Topic/CMFCToolBar::GetInvalidateItemRect.md)|클라이언트 영역의 지정 된 인덱스에 있는 단추를 다시 그릴 영역을 검색 합니다.|  
|[CMFCToolBar::GetItemID](../Topic/CMFCToolBar::GetItemID.md)|도구 모음 단추에 지정 된 인덱스의 명령 ID를 반환 합니다.|  
|[CMFCToolBar::GetItemRect](../Topic/CMFCToolBar::GetItemRect.md)|단추는 지정 된 인덱스의 경계 사각형을 반환합니다.|  
|[CMFCToolBar::GetLargeColdImages](../Topic/CMFCToolBar::GetLargeColdImages.md)|콜드 큰 도구 모음 단추 이미지 응용 프로그램에서의 컬렉션에 대 한 포인터를 반환합니다.|  
|[CMFCToolBar::GetLargeDisabledImages](../Topic/CMFCToolBar::GetLargeDisabledImages.md)|응용 프로그램에서 사용할 수 없는 큰 도구 모음 단추 이미지의 컬렉션에 대 한 포인터를 반환합니다.|  
|[CMFCToolBar::GetLargeImages](../Topic/CMFCToolBar::GetLargeImages.md)|컬렉션에 응용 프로그램에서 큰 도구 모음 단추 이미지에 대 한 포인터를 반환합니다.|  
|[CMFCToolBar::GetLockedColdImages](../Topic/CMFCToolBar::GetLockedColdImages.md)|컬렉션에 잠긴된 콜드 이미지 도구 모음에 포인터를 반환합니다.|  
|[CMFCToolBar::GetLockedDisabledImages](../Topic/CMFCToolBar::GetLockedDisabledImages.md)|컬렉션에 잠긴된 비활성된 이미지 도구 모음에 포인터를 반환합니다.|  
|[CMFCToolBar::GetLockedImages](../Topic/CMFCToolBar::GetLockedImages.md)|컬렉션에 잠금된 단추 이미지 도구 모음에 포인터를 반환합니다.|  
|[CMFCToolBar::GetLockedImageSize](../Topic/CMFCToolBar::GetLockedImageSize.md)|잠긴된 도구 모음 이미지의 기본 크기를 반환합니다.|  
|[CMFCToolBar::GetLockedMenuImages](../Topic/CMFCToolBar::GetLockedMenuImages.md)|포인터 컬렉션 잠금된 도구 모음에 도구 모음에서 메뉴 이미지를 반환합니다.|  
|[CMFCToolBar::GetMenuButtonSize](../Topic/CMFCToolBar::GetMenuButtonSize.md)|응용 프로그램에서 메뉴 단추 크기를 반환합니다.|  
|[CMFCToolBar::GetMenuImageSize](../Topic/CMFCToolBar::GetMenuImageSize.md)|응용 프로그램에서 메뉴 단추 이미지의 크기를 반환합니다.|  
|[CMFCToolBar::GetMenuImages](../Topic/CMFCToolBar::GetMenuImages.md)|컬렉션에 응용 프로그램에서 메뉴 단추 이미지에 대 한 포인터를 반환합니다.|  
|[CMFCToolBar::GetOrigButtons](../Topic/CMFCToolBar::GetOrigButtons.md)|도구 모음 단추 사용자 지정 되지 않은 컬렉션을 검색합니다.|  
|[CMFCToolBar::GetOrigResetButtons](../Topic/CMFCToolBar::GetOrigResetButtons.md)|원래 대로 사용자 지정 되지 않은 도구 모음 단추의 컬렉션을 검색합니다.|  
|[CMFCToolBar::GetResourceID](../Topic/CMFCToolBar::GetResourceID.md)|도구 모음 리소스 ID를 검색합니다.|  
|[CMFCToolBar::GetRouteCommandsViaFrame](../Topic/CMFCToolBar::GetRouteCommandsViaFrame.md)|개체, 부모 프레임 또는 소유자 결정, 도구 모음에 명령을 보냅니다.|  
|[CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)|도구 모음 단추의 높이 반환합니다.|  
|[CMFCToolBar::GetShowTooltips](../Topic/CMFCToolBar::GetShowTooltips.md)|도구 모음 단추에 도구 설명이 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBar::GetSiblingToolBar](../Topic/CMFCToolBar::GetSiblingToolBar.md)|도구 모음에 있는 형제를 검색합니다.|  
|[CMFCToolBar::GetUserImages](../Topic/CMFCToolBar::GetUserImages.md)|컬렉션에 응용 프로그램에서 사용자 정의 도구 모음 단추 이미지에 대 한 포인터를 반환합니다.|  
|[CMFCToolBar::HitTest](../Topic/CMFCToolBar::HitTest.md)|지정 된 위치에 위치한 도구 모음 단추의 인덱스를 반환 합니다.|  
|[CMFCToolBar::InsertButton](../Topic/CMFCToolBar::InsertButton.md)|도구 모음에 단추를 삽입합니다.|  
|[CMFCToolBar::InsertSeparator](../Topic/CMFCToolBar::InsertSeparator.md)|도구 모음에 구분 기호를 삽입합니다.|  
|[CMFCToolBar::InvalidateButton](../Topic/CMFCToolBar::InvalidateButton.md)|제공 된 인덱스에 있는 도구 모음 단추의 클라이언트 영역을 무효화 합니다.|  
|[CMFCToolBar::IsAddRemoveQuickCustomize](../Topic/CMFCToolBar::IsAddRemoveQuickCustomize.md)|사용자를 추가 하거나 사용 하 여 도구 모음 단추 제거 여부 결정은  **사용자 지정** 메뉴 옵션.|  
|[CMFCToolBar::IsAltCustomizeMode](../Topic/CMFCToolBar::IsAltCustomizeMode.md)|지정 여부  *빠른 사용자 지정* 사용 중인 단추를 드래그 합니다.|  
|[CMFCToolBar::IsAutoGrayInactiveImages](../Topic/CMFCToolBar::IsAutoGrayInactiveImages.md)|비활성 \(비 강조\) 단추 이미지의 자동 생성을 사용할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBar::IsBasicCommand](../Topic/CMFCToolBar::IsBasicCommand.md)|기본 명령 목록에서 명령을 결정 합니다.|  
|[CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)|도구 모음 테두리 확장 된 단추를 표시할 수 있는지 여부를 결정 합니다.|  
|[CMFCToolBar::IsButtonHighlighted](../Topic/CMFCToolBar::IsButtonHighlighted.md)|단추 도구 모음에서 강조 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBar::IsCommandPermitted](../Topic/CMFCToolBar::IsCommandPermitted.md)|명령을 허용 하는지 여부를 결정 합니다.|  
|[CMFCToolBar::IsCommandRarelyUsed](../Topic/CMFCToolBar::IsCommandRarelyUsed.md)|명령을 자주 사용 되는지 여부를 결정 \(참조 [CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)\).|  
|[CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)|도구 모음 프레임 워크에서 사용자 지정 모드 인지 여부를 지정 합니다.|  
|[CMFCToolBar::IsDragButton](../Topic/CMFCToolBar::IsDragButton.md)|도구 모음 단추를 끌고 있는지 여부를 결정 합니다.|  
|[CMFCToolBar::IsExistCustomizeButton](../Topic/CMFCToolBar::IsExistCustomizeButton.md)|도구 모음이 포함 되어 있는지 여부를 결정 하는  **사용자 지정** 단추.|  
|[CMFCToolBar::IsFloating](../Topic/CMFCToolBar::IsFloating.md)|도구 모음 이동 여부를 결정 합니다.|  
|[CMFCToolBar::IsLargeIcons](../Topic/CMFCToolBar::IsLargeIcons.md)|응용 프로그램에서 도구 모음에 현재 큰 아이콘 표시 여부를 지정 합니다.|  
|[CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md)|명령에 지정 된 도구 모음 단추에서 보낸 가장 최근에 실행 여부를 결정 합니다.|  
|[CMFCToolBar::IsLocked](../Topic/CMFCToolBar::IsLocked.md)|도구 모음이 잠겨 있는지 여부를 결정 합니다.|  
|[CMFCToolBar::IsOneRowWithSibling](../Topic/CMFCToolBar::IsOneRowWithSibling.md)|도구 모음 및 도구 모음의 형제 같은 행에 배치 됩니다 여부를 결정 합니다.|  
|[CMFCToolBar::IsUserDefined](../Topic/CMFCToolBar::IsUserDefined.md)|도구 모음 사용자 정의 인지 여부를 지정 합니다.|  
|[CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md)|이미지 도구 모음에서 응용 프로그램 리소스를 로드합니다.|  
|[CMFCToolBar::LoadBitmapEx](../Topic/CMFCToolBar::LoadBitmapEx.md)|이미지 도구 모음에서 응용 프로그램 리소스를 로드합니다.  큰 이미지를 포함 합니다.|  
|[CMFCToolBar::LoadParameters](../Topic/CMFCToolBar::LoadParameters.md)|Windows 레지스트리에서 전역 도구 모음 옵션을 로드합니다.|  
|[CMFCToolBar::LoadState](../Topic/CMFCToolBar::LoadState.md)|Windows 레지스트리에서 도구 모음 상태 정보를 로드합니다.  \(재정의 [CPane::LoadState](../Topic/CPane::LoadState.md).\)|  
|[CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md)|도구 모음에서 응용 프로그램 리소스를 로드합니다.|  
|[CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)|사용 하 여 도구 모음 응용 프로그램 리소스에서 로드 된 `CMFCToolBarInfo` 큰 이미지를 사용 하는 응용 프로그램을 사용 하는 도우미 클래스입니다.|  
|[CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md)|도구 모음에서 단추를 선택할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBar::OnFillBackground](../Topic/CMFCToolBar::OnFillBackground.md)|프레임 워크에서 호출 합니다. [CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md) 도구 모음 배경을 채울 수 있습니다.|  
|[CMFCToolBar::OnReset](../Topic/CMFCToolBar::OnReset.md)|도구 모음을 원래 상태로 복원합니다.|  
|[CMFCToolBar::OnSetAccData](../Topic/CMFCToolBar::OnSetAccData.md)|\(재정의 [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCToolBar::OnSetDefaultButtonText](../Topic/CMFCToolBar::OnSetDefaultButtonText.md)|텍스트 도구 모음 단추를 기본 상태로 복원합니다.|  
|`CMFCToolBar::OnUpdateCmdUI`|내부적으로 사용됩니다.|  
|[CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md)|도구 모음에서 모든 단추를 제거합니다.|  
|[CMFCToolBar::RemoveButton](../Topic/CMFCToolBar::RemoveButton.md)|지정 된 인덱스를 사용 하 여 단추를 도구 모음에서 제거합니다.|  
|[CMFCToolBar::RemoveStateFromRegistry](../Topic/CMFCToolBar::RemoveStateFromRegistry.md)|Windows 레지스트리에서 도구 모음에 대 한 상태 정보를 삭제합니다.|  
|[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)|다른 도구 모음 단추를를 도구 모음 단추를 바꿉니다.|  
|[CMFCToolBar::ResetAll](../Topic/CMFCToolBar::ResetAll.md)|모든 도구 모음을 원래 상태로 복원합니다.|  
|[CMFCToolBar::ResetAllImages](../Topic/CMFCToolBar::ResetAllImages.md)|응용 프로그램에서 모든 도구 모음 이미지 컬렉션을 지웁니다.|  
|[CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md)|도구 모음을 원래 상태로 복원합니다.|  
|[CMFCToolBar::SaveState](../Topic/CMFCToolBar::SaveState.md)|도구 모음에 대 한 상태 정보는 Windows 레지스트리에 저장합니다.  \(재정의 [CPane::SaveState](../Topic/CPane::SaveState.md).\)|  
|`CMFCToolBar::Serialize`|\(재정의 `CBasePane::Serialize`.\)|  
|[CMFCToolBar::SetBasicCommands](../Topic/CMFCToolBar::SetBasicCommands.md)|사용자는 메뉴를 열 때 항상 표시 되는 명령 목록을 설정 합니다.|  
|[CMFCToolBar::SetButtonInfo](../Topic/CMFCToolBar::SetButtonInfo.md)|명령 ID, 스타일 및 도구 모음 단추 이미지 ID를 설정합니다.|  
|[CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md)|도구 모음 단추의 스타일을 지정 된 인덱스를 설정합니다.|  
|[CMFCToolBar::SetButtonText](../Topic/CMFCToolBar::SetButtonText.md)|도구 모음 단추의 텍스트 레이블을 설정합니다.|  
|[CMFCToolBar::SetButtons](../Topic/CMFCToolBar::SetButtons.md)|도구 모음에 단추를 설정합니다.|  
|[CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)|드물게 사용 되는 명령을 응용 프로그램의 메뉴에 표시 되지 않습니다 지정 합니다.|  
|[CMFCToolBar::SetCustomizeMode](../Topic/CMFCToolBar::SetCustomizeMode.md)|모든 도구 모음을 응용 프로그램에서에 대 한 사용자 지정 모드를 사용할 수 있거나.|  
|[CMFCToolBar::SetGrayDisabledButtons](../Topic/CMFCToolBar::SetGrayDisabledButtons.md)|비활성화 된 단추 도구 모음에서 흐리게 표시 되어 있는지 또는 사용할 수 없는 이미지 사용 안 함된 단추를 사용 하면 지정 합니다.|  
|[CMFCToolBar::SetHeight](../Topic/CMFCToolBar::SetHeight.md)|도구 모음의 높이 설정합니다.|  
|[CMFCToolBar::SetHotBorder](../Topic/CMFCToolBar::SetHotBorder.md)|도구 모음 단추 핫 트래킹 지 여부를 지정 합니다.|  
|[CMFCToolBar::SetHotTextColor](../Topic/CMFCToolBar::SetHotTextColor.md)|바로 가기 도구 모음 단추에 대 한 텍스트 색을 설정합니다.|  
|[CMFCToolBar::SetLargeIcons](../Topic/CMFCToolBar::SetLargeIcons.md)|도구 모음 단추를 큰 아이콘 표시 여부를 지정 합니다.|  
|[CMFCToolBar::SetLockedSizes](../Topic/CMFCToolBar::SetLockedSizes.md)|도구 모음 잠금된 단추와 잠금된 이미지의 크기를 설정합니다.|  
|[CMFCToolBar::SetMenuSizes](../Topic/CMFCToolBar::SetMenuSizes.md)|메뉴 도구 모음 단추 및 해당 이미지의 크기를 설정합니다.|  
|[CMFCToolBar::SetNonPermittedCommands](../Topic/CMFCToolBar::SetNonPermittedCommands.md)|사용자가 실행할 수 없는 명령 목록을 설정 합니다.|  
|[CMFCToolBar::SetOneRowWithSibling](../Topic/CMFCToolBar::SetOneRowWithSibling.md)|도구 모음 및 형제 같은 행에 배치합니다.|  
|[CMFCToolBar::SetPermament](../Topic/CMFCToolBar::SetPermament.md)|사용자가 도구 모음을 닫을 수 있습니다 여부를 지정 합니다.|  
|[CMFCToolBar::SetRouteCommandsViaFrame](../Topic/CMFCToolBar::SetRouteCommandsViaFrame.md)|소유자 또는 부모 프레임 명령을 도구 모음으로 보낼지 여부를 지정 합니다.|  
|[CMFCToolBar::SetShowTooltips](../Topic/CMFCToolBar::SetShowTooltips.md)|프레임 워크에 도구 설명을 표시할지 여부를 지정 합니다.|  
|[CMFCToolBar::SetSiblingToolBar](../Topic/CMFCToolBar::SetSiblingToolBar.md)|형제는 도구 모음을 지정합니다.|  
|[CMFCToolBar::SetSizes](../Topic/CMFCToolBar::SetSizes.md)|모든 도구 모음 단추 및 이미지 크기를 지정합니다.|  
|[CMFCToolBar::SetToolBarBtnText](../Topic/CMFCToolBar::SetToolBarBtnText.md)|도구 모음 단추의 속성을 지정합니다.|  
|[CMFCToolBar::SetTwoRowsWithSibling](../Topic/CMFCToolBar::SetTwoRowsWithSibling.md)|도구 모음 및 형제의 별도 행에 배치합니다.|  
|[CMFCToolBar::SetUserImages](../Topic/CMFCToolBar::SetUserImages.md)|응용 프로그램에서 사용자 정의 이미지의 컬렉션을 설정합니다.|  
|[CMFCToolBar::StretchPane](../Topic/CMFCToolBar::StretchPane.md)|도구 모음을 세로 나 가로로 늘어납니다. \(재정의 [CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md).\)|  
|[CMFCToolBar::TranslateChar](../Topic/CMFCToolBar::TranslateChar.md)|지정 된 키 코드는 유효한 바로 가기 키에 해당 하는 경우 단추 명령을 실행 합니다.|  
|[CMFCToolBar::UpdateButton](../Topic/CMFCToolBar::UpdateButton.md)|지정 된 단추의 상태를 업데이트합니다.|  
|[CMFCToolBar::WrapToolBar](../Topic/CMFCToolBar::WrapToolBar.md)|지정한 크기 내에서 도구 모음 단추를 다시 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBar::AllowShowOnList](../Topic/CMFCToolBar::AllowShowOnList.md)|도구 모음 목록에 표시할지 여부를 결정의  **도구 모음** 창에서  **사용자 지정** 대화 상자.|  
|[CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md)|도구 모음에서 단추의 최대 높이 계산합니다.|  
|[CMFCToolBar::DoPaint](../Topic/CMFCToolBar::DoPaint.md)|도구 모음을 다시 그립니다.|  
|[CMFCToolBar::DrawButton](../Topic/CMFCToolBar::DrawButton.md)|도구 모음 단추를 다시 그립니다.|  
|[CMFCToolBar::DrawSeparator](../Topic/CMFCToolBar::DrawSeparator.md)|도구 모음 구분 기호를 다시 그립니다.|  
|[CMFCToolBar::OnUserToolTip](../Topic/CMFCToolBar::OnUserToolTip.md)|단추의 도구 설명 표시 되려고 할 때 프레임 워크에 의해 호출 됩니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBar::m\_bDontScaleImages](../Topic/CMFCToolBar::m_bDontScaleImages.md)|높은 DPI 모드로 조정 여부 또는 않습니다 도구 모음 이미지를 지정 합니다.|  
|[CMFCToolBar::m\_dblLargeImageRatio](../Topic/CMFCToolBar::m_dblLargeImageRatio.md)|큰 이미지의 치수 \(너비 또는 높이\)와 일반 이미지의 치수 사이의 비율을 지정합니다.|  
  
## 설명  
 통합 하는 `CMFCToolBar` 개체를 응용 프로그램으로, 다음과이 같이 하십시오.  
  
1.  추가 된 `CMFCToolBar` 주 프레임 창 개체입니다.  
  
2.  면 처리는 `WM_CREATE` 주 프레임 창에 대 한 메시지, 프로시저 호출 [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md) 또는 [CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md) 도구 모음을 만들고 스타일을 지정 합니다.  
  
3.  호출 [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) 도킹 스타일을 지정할 수 있습니다.  
  
 특수 단추를 삽입 하려면 콤보 상자 또는 드롭다운 도구 모음 같은 더미 단추 부모 리소스에서를 예약 하 고 런타임에 더미 단추를 사용 하 여 대체 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  자세한 내용은 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오.  
  
 `CMFCToolBar`MFC 라이브러리 클래스를 기본 클래스인 [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md), [CMFCPopupMenuBar 클래스](../../mfc/reference/cmfcpopupmenubar-class.md), 및 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCToolBar` 클래스입니다.  예제 텍스트 창 레이블 도구 모음 설정, 테두리 설정 창의 스타일 설정 하 고 사용 하는 방법을 보여 줍니다.는  **단추 추가 \/ 제거** 단추는 도구 모음 끝에 나타납니다.  이 코드 조각에 속해 있는  [IE 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#6](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#8](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_2.cpp)]  
  
## 요구 사항  
 **헤더:** afxtoolbar.h  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md)   
 [CMFCPopupMenuBar 클래스](../../mfc/reference/cmfcpopupmenubar-class.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)