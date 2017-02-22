---
title: "CToolBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl class"
  - "도구 설명[C++], 알림"
  - "도구 모음 컨트롤[MFC], CToolBarCtrl class"
  - "Windows common controls [C++], CToolBarCtrl"
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CToolBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 도구 모음 공용 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CToolBarCtrl::CToolBarCtrl](../Topic/CToolBarCtrl::CToolBarCtrl.md)|`CToolBarCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CToolBarCtrl::AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)|하나 이상의 비트맵 단추 이미지 도구 모음 컨트롤에 사용할 수 있는 단추 이미지 목록에 추가합니다.|  
|[CToolBarCtrl::AddButtons](../Topic/CToolBarCtrl::AddButtons.md)|도구 모음 컨트롤에 하나 이상의 단추를 추가합니다.|  
|[CToolBarCtrl::AddString](../Topic/CToolBarCtrl::AddString.md)|도구 모음의 내부 목록 문자열 리소스 ID로 전달 하는 새 문자열을 추가 합니다.|  
|[CToolBarCtrl::AddStrings](../Topic/CToolBarCtrl::AddStrings.md)|문자열, 문자열 도구 모음의 내부 목록에 null 구분 된 문자열 버퍼를 포인터로 전달 하거나 새 문자열을 추가 합니다.|  
|[CToolBarCtrl::AutoSize](../Topic/CToolBarCtrl::AutoSize.md)|도구 모음 컨트롤 크기를 조정 합니다.|  
|[CToolBarCtrl::ChangeBitmap](../Topic/CToolBarCtrl::ChangeBitmap.md)|현재 도구 모음 컨트롤에는 단추에 대 한 비트맵을 변경합니다.|  
|[CToolBarCtrl::CheckButton](../Topic/CToolBarCtrl::CheckButton.md)|확인 또는 지정 된 단추는 도구 모음 컨트롤에서을 지웁니다.|  
|[CToolBarCtrl::CommandToIndex](../Topic/CToolBarCtrl::CommandToIndex.md)|지정한 명령 식별자와 연결 된 단추의 인덱스를 검색 합니다.|  
|[CToolBarCtrl::Create](../Topic/CToolBarCtrl::Create.md)|Toolbar 컨트롤을 만들고이에 연결 된 `CToolBarCtrl` 개체입니다.|  
|[CToolBarCtrl::CreateEx](../Topic/CToolBarCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 도구 모음 컨트롤을 만들고 연결 하는 `CToolBarCtrl` 개체입니다.|  
|[CToolBarCtrl::Customize](../Topic/CToolBarCtrl::Customize.md)|도구 모음 사용자 지정 대화 상자를 표시합니다.|  
|[CToolBarCtrl::DeleteButton](../Topic/CToolBarCtrl::DeleteButton.md)|Toolbar 컨트롤에서 단추를 삭제합니다.|  
|[CToolBarCtrl::EnableButton](../Topic/CToolBarCtrl::EnableButton.md)|Toolbar 컨트롤에서 단추를 사용할 수 있거나.|  
|[CToolBarCtrl::GetAnchorHighlight](../Topic/CToolBarCtrl::GetAnchorHighlight.md)|앵커 강조 표시 도구 모음에 대 한 설정을 검색 합니다.|  
|[CToolBarCtrl::GetBitmap](../Topic/CToolBarCtrl::GetBitmap.md)|인덱스 도구 모음에서 단추와 연결 된 비트맵을 검색 합니다.|  
|[CToolBarCtrl::GetBitmapFlags](../Topic/CToolBarCtrl::GetBitmapFlags.md)|도구 모음 비트맵을 연결 된 플래그를 가져옵니다.|  
|[CToolBarCtrl::GetButton](../Topic/CToolBarCtrl::GetButton.md)|지정 된 단추는 도구 모음 컨트롤에 대 한 정보를 검색합니다.|  
|[CToolBarCtrl::GetButtonCount](../Topic/CToolBarCtrl::GetButtonCount.md)|단추 도구 모음 컨트롤에 현재 개수를 검색합니다.|  
|[CToolBarCtrl::GetButtonInfo](../Topic/CToolBarCtrl::GetButtonInfo.md)|도구 모음에서 단추에 대 한 정보를 검색합니다.|  
|[CToolBarCtrl::GetButtonSize](../Topic/CToolBarCtrl::GetButtonSize.md)|현재 폭과 높이를 픽셀 단위로 도구 모음 단추 중 하나를 검색합니다.|  
|[CToolBarCtrl::GetColorScheme](../Topic/CToolBarCtrl::GetColorScheme.md)|현재 도구 모음 컨트롤의 색 구성표를 검색합니다.|  
|[CToolBarCtrl::GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md)|디스플레이 사용 안 함 단추를 도구 모음 컨트롤을 사용 하 여 이미지 목록을 검색 합니다.|  
|[CToolBarCtrl::GetDropTarget](../Topic/CToolBarCtrl::GetDropTarget.md)|검색 된  [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) 도구 모음 컨트롤에 대 한 인터페이스.|  
|[CToolBarCtrl::GetExtendedStyle](../Topic/CToolBarCtrl::GetExtendedStyle.md)|도구 모음 컨트롤에 대 한 확장된 스타일을 검색합니다.|  
|[CToolBarCtrl::GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md)|"활성" 단추를 표시 하려면 도구 모음 컨트롤을 사용 하 여 이미지 목록을 검색 합니다.  위에 마우스 포인터를 놓을 때 핫스폿 단추 강조 표시 됩니다.|  
|[CToolBarCtrl::GetHotItem](../Topic/CToolBarCtrl::GetHotItem.md)|도구 모음에서 바로 가기 항목의 인덱스를 검색합니다.|  
|[CToolBarCtrl::GetImageList](../Topic/CToolBarCtrl::GetImageList.md)|도구 모음 컨트롤을 사용 하 여 기본 상태로 단추를 표시할 수 있는 이미지 목록을 검색 합니다.|  
|[CToolBarCtrl::GetInsertMark](../Topic/CToolBarCtrl::GetInsertMark.md)|현재 삽입 표시 도구 모음에 대 한 검색합니다.|  
|[CToolBarCtrl::GetInsertMarkColor](../Topic/CToolBarCtrl::GetInsertMarkColor.md)|도구 모음의 삽입 표시를 그리는 데 사용 되는 색을 검색 합니다.|  
|[CToolBarCtrl::GetItemRect](../Topic/CToolBarCtrl::GetItemRect.md)|단추를 도구 모음 컨트롤의 경계 사각형을 검색합니다.|  
|[CToolBarCtrl::GetMaxSize](../Topic/CToolBarCtrl::GetMaxSize.md)|전체 크기의 모두 표시 단추 및 도구 모음에 구분 기호를 검색합니다.|  
|[CToolBarCtrl::GetMaxTextRows](../Topic/CToolBarCtrl::GetMaxTextRows.md)|도구 모음 단추에 표시 되는 텍스트 행의 최대 수를 검색 합니다.|  
|[CToolBarCtrl::GetMetrics](../Topic/CToolBarCtrl::GetMetrics.md)|메트릭 도구 모음 컨트롤을 검색합니다.|  
|[CToolBarCtrl::GetPadding](../Topic/CToolBarCtrl::GetPadding.md)|현재 도구 모음 컨트롤의 가로 및 세로 안쪽을 검색합니다.|  
|[CToolBarCtrl::GetPressedImageList](../Topic/CToolBarCtrl::GetPressedImageList.md)|현재 도구 모음 컨트롤에 있는 누름된 상태의 단추를 사용 하 여 이미지 목록을 검색 합니다.|  
|[CToolBarCtrl::GetRect](../Topic/CToolBarCtrl::GetRect.md)|지정 된 도구 모음 단추의 경계 사각형을 검색합니다.|  
|[CToolBarCtrl::GetRows](../Topic/CToolBarCtrl::GetRows.md)|현재 도구 모음에 표시 되는 단추의 행 개수를 검색 합니다.|  
|[CToolBarCtrl::GetState](../Topic/CToolBarCtrl::GetState.md)|이 활성화, 눌렀을 인지 체크의 도구 모음 컨트롤에서 단추 상태에 대 한 정보를 검색 합니다.|  
|[CToolBarCtrl::GetString](../Topic/CToolBarCtrl::GetString.md)|도구 모음의 문자열을 검색합니다.|  
|[CToolBarCtrl::GetStyle](../Topic/CToolBarCtrl::GetStyle.md)|현재 사용 하는 도구 모음 컨트롤에 스타일을 검색합니다.|  
|[CToolBarCtrl::GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md)|연결 된 경우 도구 모음 컨트롤에 도구 설명 컨트롤의 핸들을 검색 합니다.|  
|[CToolBarCtrl::HideButton](../Topic/CToolBarCtrl::HideButton.md)|도구 모음 컨트롤에 지정 된 단추를 표시 하거나 숨깁니다.|  
|[CToolBarCtrl::HitTest](../Topic/CToolBarCtrl::HitTest.md)|위치에서 도구 모음 컨트롤 포인트가 결정 합니다.|  
|[CToolBarCtrl::Indeterminate](../Topic/CToolBarCtrl::Indeterminate.md)|설정 하거나 비활성화 된 상태 \(회색\) 단추는 도구 모음 컨트롤을 지웁니다.|  
|[CToolBarCtrl::InsertButton](../Topic/CToolBarCtrl::InsertButton.md)|Toolbar 컨트롤에 단추를 삽입합니다.|  
|[CToolBarCtrl::InsertMarkHitTest](../Topic/CToolBarCtrl::InsertMarkHitTest.md)|도구 모음에는 요소에 대 한 삽입 표시 정보를 검색합니다.|  
|[CToolBarCtrl::IsButtonChecked](../Topic/CToolBarCtrl::IsButtonChecked.md)|지정 된 단추는 도구 모음 컨트롤에 선택 되어 있는지 여부를 알려 줍니다.|  
|[CToolBarCtrl::IsButtonEnabled](../Topic/CToolBarCtrl::IsButtonEnabled.md)|지정 된 단추는 도구 모음 컨트롤에 사용할 수 있는지 여부를 알려 줍니다.|  
|[CToolBarCtrl::IsButtonHidden](../Topic/CToolBarCtrl::IsButtonHidden.md)|도구 모음 컨트롤에 지정 된 단추를 숨길지 여부를 지정 합니다.|  
|[CToolBarCtrl::IsButtonHighlighted](../Topic/CToolBarCtrl::IsButtonHighlighted.md)|강조 도구 모음 단추의 상태를 확인합니다.|  
|[CToolBarCtrl::IsButtonIndeterminate](../Topic/CToolBarCtrl::IsButtonIndeterminate.md)|도구 모음 컨트롤에 지정 된 단추의 상태를 비활성화 \(회색\) 인지 여부를 알려 줍니다.|  
|[CToolBarCtrl::IsButtonPressed](../Topic/CToolBarCtrl::IsButtonPressed.md)|도구 모음 컨트롤에 지정 된 단추를 눌렀는지 여부를 지정 합니다.|  
|[CToolBarCtrl::LoadImages](../Topic/CToolBarCtrl::LoadImages.md)|도구 모음 컨트롤이 이미지 목록으로 비트맵을 로드합니다.|  
|[CToolBarCtrl::MapAccelerator](../Topic/CToolBarCtrl::MapAccelerator.md)|도구 모음 단추에 액셀러레이터 문자를 매핑합니다.|  
|[CToolBarCtrl::MarkButton](../Topic/CToolBarCtrl::MarkButton.md)|도구 모음 컨트롤에 지정 된 단추는 강조 표시 상태를 설정합니다.|  
|[CToolBarCtrl::MoveButton](../Topic/CToolBarCtrl::MoveButton.md)|단추 하나의 인덱스에서 다른 위치로 이동합니다.|  
|[CToolBarCtrl::PressButton](../Topic/CToolBarCtrl::PressButton.md)|키를 누르거나 도구 모음 컨트롤에 지정 된 단추를 해제 합니다.|  
|[CToolBarCtrl::ReplaceBitmap](../Topic/CToolBarCtrl::ReplaceBitmap.md)|현재 도구 모음 컨트롤에 기존 비트맵 새 비트맵으로 대체합니다.|  
|[CToolBarCtrl::RestoreState](../Topic/CToolBarCtrl::RestoreState.md)|도구 모음 컨트롤의 상태를 복원합니다.|  
|[CToolBarCtrl::SaveState](../Topic/CToolBarCtrl::SaveState.md)|도구 모음 컨트롤의 상태를 저장합니다.|  
|[CToolBarCtrl::SetAnchorHighlight](../Topic/CToolBarCtrl::SetAnchorHighlight.md)|도구 모음에 대 한 설정 앵커 강조 표시를 설정 합니다.|  
|[CToolBarCtrl::SetBitmapSize](../Topic/CToolBarCtrl::SetBitmapSize.md)|도구 모음 컨트롤을 추가 하려면 비트맵 이미지의 크기를 설정 합니다.|  
|[CToolBarCtrl::SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)|도구 모음에서 기존 단추에 대 한 정보를 설정합니다.|  
|[CToolBarCtrl::SetButtonSize](../Topic/CToolBarCtrl::SetButtonSize.md)|컨트롤 도구 모음에 추가할 단추 크기를 설정 합니다.|  
|[CToolBarCtrl::SetButtonStructSize](../Topic/CToolBarCtrl::SetButtonStructSize.md)|크기를 지정 된 `TBBUTTON` 구조.|  
|[CToolBarCtrl::SetButtonWidth](../Topic/CToolBarCtrl::SetButtonWidth.md)|Toolbar 컨트롤에 단추를 최소 및 최대 너비를 설정합니다.|  
|[CToolBarCtrl::SetCmdID](../Topic/CToolBarCtrl::SetCmdID.md)|소유자 창으로 지정 된 단추를 누를 때 보낼 명령 식별자를 설정 합니다.|  
|[CToolBarCtrl::SetColorScheme](../Topic/CToolBarCtrl::SetColorScheme.md)|현재 도구 모음 컨트롤의 색 구성표를 설정합니다.|  
|[CToolBarCtrl::SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)|도구 모음 컨트롤을 사용 하는 이미지 목록 표시 해제 단추를 설정 합니다.|  
|[CToolBarCtrl::SetDrawTextFlags](../Topic/CToolBarCtrl::SetDrawTextFlags.md)|Win32 함수에는 플래그를 설정 합니다.  [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), 플래그 설정 방법에 따라 형식이 지정 된 사각형 안에 텍스트를 그리는 데 사용 됩니다.|  
|[CToolBarCtrl::SetExtendedStyle](../Topic/CToolBarCtrl::SetExtendedStyle.md)|도구 모음 컨트롤에 대 한 확장된 스타일을 설정합니다.|  
|[CToolBarCtrl::SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)|도구 모음 컨트롤 "활성" 단추를 표시 하는 데 사용할 이미지 목록을 설정 합니다.|  
|[CToolBarCtrl::SetHotItem](../Topic/CToolBarCtrl::SetHotItem.md)|도구 모음에서 바로 가기 항목을 설정합니다.|  
|[CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md)|도구 모음은 기본 상태는 단추를 표시 하는 데 사용할 이미지 목록을 설정 합니다.|  
|[CToolBarCtrl::SetIndent](../Topic/CToolBarCtrl::SetIndent.md)|들여쓰기의 첫 번째 단추를 도구 모음 컨트롤에 설정합니다.|  
|[CToolBarCtrl::SetInsertMark](../Topic/CToolBarCtrl::SetInsertMark.md)|현재 삽입 표시 도구 모음을 설정합니다.|  
|[CToolBarCtrl::SetInsertMarkColor](../Topic/CToolBarCtrl::SetInsertMarkColor.md)|도구 모음의 삽입 표시를 그리는 데 사용 되는 색을 설정 합니다.|  
|[CToolBarCtrl::SetMaxTextRows](../Topic/CToolBarCtrl::SetMaxTextRows.md)|도구 모음 단추에 표시 되는 텍스트 행의 최대 수를 설정 합니다.|  
|[CToolBarCtrl::SetMetrics](../Topic/CToolBarCtrl::SetMetrics.md)|메트릭 도구 모음 컨트롤에 설정합니다.|  
|[CToolBarCtrl::SetOwner](../Topic/CToolBarCtrl::SetOwner.md)|창 도구 모음 컨트롤에서 알림 메시지를 받도록 설정 합니다.|  
|[CToolBarCtrl::SetPadding](../Topic/CToolBarCtrl::SetPadding.md)|현재 도구 모음 컨트롤의 가로 및 세로 여백을 설정합니다.|  
|[CToolBarCtrl::SetPressedImageList](../Topic/CToolBarCtrl::SetPressedImageList.md)|현재 도구 모음 컨트롤에 있는 누름된 상태의 단추를 사용 하 여 이미지 목록을 설정 합니다.|  
|[CToolBarCtrl::SetRows](../Topic/CToolBarCtrl::SetRows.md)|도구 모음에 표시 되는 단추의 행 개수를 설정 합니다.|  
|[CToolBarCtrl::SetState](../Topic/CToolBarCtrl::SetState.md)|도구 모음 컨트롤에 지정 된 단추의 상태를 설정합니다.|  
|[CToolBarCtrl::SetStyle](../Topic/CToolBarCtrl::SetStyle.md)|도구 모음 컨트롤에 대 한 스타일 설정입니다.|  
|[CToolBarCtrl::SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md)|도구 설명 컨트롤에 도구 모음 컨트롤과 연결합니다.|  
|[CToolBarCtrl::SetWindowTheme](../Topic/CToolBarCtrl::SetWindowTheme.md)|도구 모음 컨트롤의 시각적 스타일을 설정합니다.|  
  
## 설명  
 이 컨트롤 \(즉의 `CToolBarCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 Windows 도구 모음 공용 컨트롤 단추를 하나 이상 포함 하는 사각형 자식 창입니다.  이러한 단추는 비트맵 이미지 또는 문자열을 표시할 수 있습니다.  사용자가 특정 단추를 선택할 때 명령 메시지를 도구 모음의 소유자 창으로 보냅니다.  일반적으로 단추를 도구 모음에 응용 프로그램의 메뉴 항목에 해당. 사용자가 응용 프로그램의 명령에 액세스할 수 있는 빠른 방법을 제공 합니다.  
  
 `CToolBarCtrl`몇 가지 중요 한 내부 데이터 구조의 개체를 포함: 단추 이미지 비트맵 또는 이미지 목록, 단추 레이블 문자열 목록을 목록과 목록 `TBBUTTON` 는 이미지 연결 및\/또는 문자열의 위치와 스타일, 구조 상태 및 명령 단추의 ID.  각 요소는 이러한 데이터 구조의 인덱스에서 라고 합니다.  사용 하기 전에 `CToolBarCtrl` 개체에서 이러한 데이터 구조를 설정 해야 합니다.  문자열 목록은 단추 레이블은 사용할 수 있습니다. 도구 모음에서 문자열을 검색할 수 없습니다.  
  
 사용 하는 `CToolBarCtrl` 개체를이 같이 일반적으로 수행 됩니다.  
  
1.  생성 된 `CToolBarCtrl` 개체입니다.  
  
2.  호출  [만들기](../Topic/CToolBarCtrl::Create.md) Windows 도구 모음 공용 컨트롤을 만들고 연결할 수 있는 `CToolBarCtrl` 개체입니다.  같은 스타일을 사용 하 여 도구 모음의 스타일을 나타내는  **TBSTYLE\_TRANSPARENT** 도구 모음의 투명 또는  **TBSTYLE\_DROPDOWN** 도구 모음의 스타일 드롭다운 단추를 지 원하는.  
  
3.  단추 도구 모음을 표시 하는 방법을 식별 합니다.  
  
    -   비트맵 이미지 단추를 사용 하는 단추 비트맵 도구 모음으로 호출 하 여 추가  [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md).  
  
    -   호출 하 여 단추에 대 한 이미지 목록에서 표시 되는 이미지를 사용 하려면 이미지 목록 지정  [SetImageList](../Topic/CToolBarCtrl::SetImageList.md),  [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md), 또는  [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md).  
  
    -   단추에 대 한 레이블 문자열을 사용 하는 문자열 도구 모음으로 호출 하 여 추가  [AddString](../Topic/CToolBarCtrl::AddString.md) 또는  [AddStrings](../Topic/CToolBarCtrl::AddStrings.md).  
  
4.  호출 하 여 도구 모음에 단추 구조 추가  [AddButtons](../Topic/CToolBarCtrl::AddButtons.md).  
  
5.  도구 설명 된 소유자 창에 도구 모음 단추를 원하는 경우는 `CFrameWnd`, 처리 해야 할는  **TTN\_NEEDTEXT** 의 설명에 따라 도구 모음의 소유자 창의 메시지  [도구 팁 알림을 처리](../../mfc/handling-tool-tip-notifications.md).  도구 모음의 부모 창에서 파생 된 경우 `CFrameWnd`, 도구 설명 표시 부가적인 노력을 하지 않고 있기 때문에 `CFrameWnd` 기본 처리기를 제공 합니다.  
  
6.  도구 모음을 사용자 지정할 수 있도록 하려면의 설명에 따라 소유자 창에 사용자 지정 알림 메시지를 처리할  [사용자 지정 알림 메시지 처리](../../mfc/handling-customization-notifications.md).  
  
 사용할 수 있습니다  [SaveState](../Topic/CToolBarCtrl::SaveState.md) 도구 모음 컨트롤의 현재 상태를 저장 하 고  [RestoreState](../Topic/CToolBarCtrl::RestoreState.md) 이전에 레지스트리에 저장 된 정보를 기반으로 상태를 복원 합니다.  사용자가 나중에 사용자가 도구 모음을 원래 상태로 복원 하려는 경우 도구 모음 사용자 지정을 시작 하기 전에 간에 사용 하는 응용 프로그램의 도구 모음 상태를 저장 하는 것 외에 응용 프로그램은 일반적으로 상태 저장.  
  
## Internet Explorer 버전 4.0 이상에 대 한 지원  
 Internet Explorer, 버전 4.0 및 나중에 도입 된 기능을 지원 하기 위해 MFC 이미지 목록 지원 및 투명 한 평면 스타일 도구 모음 컨트롤에 대 한 제공 합니다.  
  
 투명 도구 모음 클라이언트를 도구 모음에서 볼 수 있습니다.  투명 도구 모음을 만들려면 모두 사용  **TBSTYLE\_FLAT** 및  **TBSTYLE\_TRANSPARENT** 스타일입니다.  도구 모음을 투명 하 게 핫 추적 기능. 즉, 도구 모음에서 핫스폿 단추 위로 마우스 포인터를 이동할 때 단추의 모양을 변경 합니다.  도구 모음을 만들 뿐만 아니라  **TBSTYLE\_FLAT** 스타일 투명 하지 않은 단추를 포함 합니다.  
  
 이미지 목록 지원을 기본 동작, 핫 이미지 및 이미지를 사용할 수 없는 컨트롤 융통성이 있습니다.  사용  [GetImageList](../Topic/CToolBarCtrl::GetImageList.md),  [GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md), 및  [GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md) 해당 상태에 따라 이미지를 조작 하는 투명 도구 모음 사용:  
  
 사용에 대 한 자세한 내용은 `CToolBarCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CToolBarCtrl 사용](../../mfc/using-ctoolbarctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC MFCIE 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)