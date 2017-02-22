---
title: "COleControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControl class"
  - "컨트롤[MFC], OLE"
  - "컨트롤[MFC], windowless"
  - "OLE 컨트롤, MFC"
  - "windowless controls"
  - "windowless controls, MFC"
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# COleControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 컨트롤 개발에 대 한 강력한 기본 클래스입니다.  
  
## 구문  
  
```  
class COleControl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleControl::COleControl](../Topic/COleControl::COleControl.md)|`COleControl` 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleControl::AmbientAppearance](../Topic/COleControl::AmbientAppearance.md)|컨트롤의 현재 모양을 검색합니다.|  
|[COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)|앰비언트 BackColor 속성의 값을 반환 합니다.|  
|[COleControl::AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)|지정 된 컨트롤의 컨테이너에서 반환합니다.|  
|[COleControl::AmbientFont](../Topic/COleControl::AmbientFont.md)|앰비언트 글꼴 속성의 값을 반환 합니다.|  
|[COleControl::AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)|앰비언트 ForeColor 속성의 값을 반환 합니다.|  
|[COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)|컨테이너의 로캘 ID를 반환합니다.|  
|[COleControl::AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)|컨테이너에서 사용 되는 단위를 반환 합니다.|  
|[COleControl::AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)|잡기 핸들을 표시할지 여부를 결정 합니다.|  
|[COleControl::AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)|해칭 표시할지 여부를 결정 합니다.|  
|[COleControl::AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)|컨테이너에서 지정 된 텍스트 맞춤 형식을 반환 합니다.|  
|[COleControl::AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)|컨트롤 사용자 인터페이스 동작에 응답 해야 하는 경우를 결정 합니다.|  
|[COleControl::AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)|컨테이너의 모드를 결정 합니다.|  
|[COleControl::BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md)|컨테이너에 바인딩된 속성이 변경 되었음을 알립니다.|  
|[COleControl::BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md)|속성 값을 편집 하려면 요청 권한입니다.|  
|[COleControl::ClientToParent](../Topic/COleControl::ClientToParent.md)|점 점 컨테이너의 원점 기준으로 컨트롤의 원점 기준으로 변환합니다.|  
|[COleControl::ClipCaretRect](../Topic/COleControl::ClipCaretRect.md)|이 컨트롤에 겹치는 경우 캐럿 사각형을 조정 합니다.|  
|[COleControl::ControlInfoChanged](../Topic/COleControl::ControlInfoChanged.md)|컨트롤에서 처리 니모닉 집합이 변경 후이 함수를 호출 합니다.|  
|[COleControl::DisplayError](../Topic/COleControl::DisplayError.md)|주식 오류 이벤트가 컨트롤의 사용자에 게 표시 됩니다.|  
|[COleControl::DoClick](../Topic/COleControl::DoClick.md)|구현 주식 `DoClick` 메서드.|  
|[COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)|속성을 serialize 하는 `COleControl` 개체입니다.|  
|[COleControl::DoSuperclassPaint](../Topic/COleControl::DoSuperclassPaint.md)|Windows 컨트롤을 서브클래싱 되었는지 OLE 컨트롤을 다시 그립니다.|  
|[COleControl::EnableSimpleFrame](../Topic/COleControl::EnableSimpleFrame.md)|단순 프레임 컨트롤을 지원할을 수 있습니다.|  
|[COleControl::ExchangeExtent](../Topic/COleControl::ExchangeExtent.md)|컨트롤의 너비와 높이 serialize합니다.|  
|[COleControl::ExchangeStockProps](../Topic/COleControl::ExchangeStockProps.md)|컨트롤의 스톡 속성을 serialize합니다.|  
|[COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md)|컨트롤의 버전 번호를 serialize합니다.|  
|[COleControl::FireClick](../Topic/COleControl::FireClick.md)|발생 주식 `Click` 이벤트.|  
|[COleControl::FireDblClick](../Topic/COleControl::FireDblClick.md)|발생 주식 `DblClick` 이벤트.|  
|[COleControl::FireError](../Topic/COleControl::FireError.md)|발생 주식 `Error` 이벤트.|  
|[COleControl::FireEvent](../Topic/COleControl::FireEvent.md)|사용자 지정 이벤트를 발생 시킵니다.|  
|[COleControl::FireKeyDown](../Topic/COleControl::FireKeyDown.md)|발생 주식 `KeyDown` 이벤트.|  
|[COleControl::FireKeyPress](../Topic/COleControl::FireKeyPress.md)|발생 주식 `KeyPress` 이벤트.|  
|[COleControl::FireKeyUp](../Topic/COleControl::FireKeyUp.md)|발생 주식 `KeyUp` 이벤트.|  
|[COleControl::FireMouseDown](../Topic/COleControl::FireMouseDown.md)|발생 주식 `MouseDown` 이벤트.|  
|[COleControl::FireMouseMove](../Topic/COleControl::FireMouseMove.md)|발생 주식 `MouseMove` 이벤트.|  
|[COleControl::FireMouseUp](../Topic/COleControl::FireMouseUp.md)|발생 주식 `MouseUp` 이벤트.|  
|[COleControl::FireReadyStateChange](../Topic/COleControl::FireReadyStateChange.md)|컨트롤의 상태가 변경 될 때 이벤트를 발생 시킵니다.|  
|[COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md)|기본 활성화 동작을 지 원하는 컨트롤의 변경 된 `IPointerInactive` 인터페이스.|  
|[COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md)|지정 된 앰비언트 속성의 값을 반환 합니다.|  
|[COleControl::GetAppearance](../Topic/COleControl::GetAppearance.md)|스톡 모양 속성의 값을 반환 합니다.|  
|[COleControl::GetBackColor](../Topic/COleControl::GetBackColor.md)|주식 BackColor 속성의 값을 반환 합니다.|  
|[COleControl::GetBorderStyle](../Topic/COleControl::GetBorderStyle.md)|주식 BorderStyle 속성의 값을 반환 합니다.|  
|[COleControl::GetCapture](../Topic/COleControl::GetCapture.md)|창 없는 컨트롤로 활성화 된 개체에 마우스 캡처가 있는지 여부를 결정 합니다.|  
|[COleControl::GetClassID](../Topic/COleControl::GetClassID.md)|컨트롤의 OLE 클래스 ID를 검색합니다.|  
|[COleControl::GetClientOffset](../Topic/COleControl::GetClientOffset.md)|컨트롤의 사각형 영역의 왼쪽된 위 모서리와의 클라이언트 영역의 왼쪽된 위 모서리의 차이 검색합니다.|  
|[COleControl::GetClientRect](../Topic/COleControl::GetClientRect.md)|컨트롤의 클라이언트 영역 크기를 검색합니다.|  
|[COleControl::GetClientSite](../Topic/COleControl::GetClientSite.md)|포인터가 해당 컨테이너 내에서 현재 클라이언트 사이트에 대 한 개체를 쿼리합니다.|  
|[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)|컨트롤 플래그 설정을 검색합니다.|  
|[COleControl::GetControlSize](../Topic/COleControl::GetControlSize.md)|OLE 컨트롤의 크기와 위치를 반환합니다.|  
|[COleControl::GetDC](../Topic/COleControl::GetDC.md)|창 없는 컨트롤 컨테이너에서 장치 컨텍스트를 얻을 수 있는 방법을 제공 합니다.|  
|[COleControl::GetEnabled](../Topic/COleControl::GetEnabled.md)|스톡 Enabled 속성의 값을 반환 합니다.|  
|[COleControl::GetExtendedControl](../Topic/COleControl::GetExtendedControl.md)|확장된 컨트롤 컨테이너에 속하는 개체에 대 한 포인터를 검색 합니다.|  
|[COleControl::GetFocus](../Topic/COleControl::GetFocus.md)|컨트롤에 포커스가 있는지 여부를 결정 합니다.|  
|[COleControl::GetFont](../Topic/COleControl::GetFont.md)|스톡 Font 속성의 값을 반환 합니다.|  
|[COleControl::GetFontTextMetrics](../Topic/COleControl::GetFontTextMetrics.md)|메트릭을 반환 된 `CFontHolder` 개체입니다.|  
|[COleControl::GetForeColor](../Topic/COleControl::GetForeColor.md)|ForeColor 스톡 속성의 값을 반환 합니다.|  
|[COleControl::GetHwnd](../Topic/COleControl::GetHwnd.md)|주식 hWnd 속성 값을 반환합니다.|  
|[COleControl::GetMessageString](../Topic/COleControl::GetMessageString.md)|메뉴 항목에 대 한 상태 표시줄 텍스트를 제공합니다.|  
|[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)|사용자가 컨트롤의 속성 값에 액세스할 수 없습니다.|  
|[COleControl::GetReadyState](../Topic/COleControl::GetReadyState.md)|컨트롤의 준비 상태를 반환합니다.|  
|[COleControl::GetRectInContainer](../Topic/COleControl::GetRectInContainer.md)|컨테이너를 기준으로 컨트롤의 사각형을 반환합니다.|  
|[COleControl::GetStockTextMetrics](../Topic/COleControl::GetStockTextMetrics.md)|메트릭 스톡 Font 속성을 반환합니다.|  
|[COleControl::GetText](../Topic/COleControl::GetText.md)|스톡 텍스트 또는 캡션 속성의 값을 반환 합니다.|  
|[COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md)|창 없는 컨트롤의 대상으로 끌어서 놓기 작업을 허용 하도록 재정의 합니다.|  
|[COleControl::InitializeIIDs](../Topic/COleControl::InitializeIIDs.md)|기본 클래스를의 컨트롤을 사용 하는 Iid 알립니다.|  
|[COleControl::InternalGetFont](../Topic/COleControl::InternalGetFont.md)|반환 된 `CFontHolder` 스톡 글꼴 속성에 대 한 개체.|  
|[COleControl::InternalGetText](../Topic/COleControl::InternalGetText.md)|스톡 텍스트 또는 캡션 속성을 검색합니다.|  
|[COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md)|컨트롤의 준비 상태를 설정 하 고 준비 상태 변경 이벤트를 발생 시킵니다.|  
|[COleControl::InvalidateControl](../Topic/COleControl::InvalidateControl.md)|다시 그릴 수 있도록 그 원인이 표시 된 컨트롤의 영역을 무효화 합니다.|  
|[COleControl::InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)|지정 된 영역 내에서 컨테이너 창의 클라이언트 영역을 무효화합니다.  영역에 창 없는 컨트롤을 다시 그리는 데 사용할 수 있습니다.|  
|[COleControl::IsConvertingVBX](../Topic/COleControl::IsConvertingVBX.md)|특수 OLE 컨트롤 로드 수 있습니다.|  
|[COleControl::IsModified](../Topic/COleControl::IsModified.md)|컨트롤 상태가 변경 되었는지 여부를 결정 합니다.|  
|[COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md)|컨테이너 현재 드로잉 작업을 위해 최적화 된 그리기를 지원 하는지 여부를 나타냅니다.|  
|[COleControl::IsSubclassedControl](../Topic/COleControl::IsSubclassedControl.md)|호출 컨트롤 서브 클래스 Windows 제어 하는 경우를 확인 합니다.|  
|[COleControl::Load](../Topic/COleControl::Load.md)|이전 비동기 데이터를 다시 설정 하 고 컨트롤의 비동기 속성의 새 로드를 시작 합니다.|  
|[COleControl::LockInPlaceActive](../Topic/COleControl::LockInPlaceActive.md)|컨테이너에서 컨트롤을 비활성화할 수 있습니다 경우 결정 합니다.|  
|[COleControl::OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md)|앰비언트 속성이 변경 될 때 호출 됩니다.|  
|[COleControl::OnAppearanceChanged](../Topic/COleControl::OnAppearanceChanged.md)|주식 모양 속성이 변경 되 면 호출 됩니다.|  
|[COleControl::OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md)|주식 BackColor 속성이 변경 될 때 호출 됩니다.|  
|[COleControl::OnBorderStyleChanged](../Topic/COleControl::OnBorderStyleChanged.md)|주식 BorderStyle 속성이 변경 될 때 호출 됩니다.|  
|[COleControl::OnClick](../Topic/COleControl::OnClick.md)|라는 주식 클릭을 발생 시키는 이벤트.|  
|[COleControl::OnClose](../Topic/COleControl::OnClose.md)|알립니다 컨트롤은 `IOleControl::Close` 호출 된.|  
|[COleControl::OnDoVerb](../Topic/COleControl::OnDoVerb.md)|제어 동사를 실행 한 후에 호출 됩니다.|  
|[COleControl::OnDraw](../Topic/COleControl::OnDraw.md)|컨트롤을 그리도록 요청할 때 호출 됩니다.|  
|[COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)|컨트롤 메타 파일 디바이스 컨텍스트를 사용 하 여 그리도록 요청할 때 컨테이너에 의해 호출 됩니다.|  
|[COleControl::OnEdit](../Topic/COleControl::OnEdit.md)|UI를 활성화 하는 컨테이너는 OLE 컨트롤에서 호출합니다.|  
|[COleControl::OnEnabledChanged](../Topic/COleControl::OnEnabledChanged.md)|스톡 Enabled 속성이 변경 될 때 호출 됩니다.|  
|[COleControl::OnEnumVerbs](../Topic/COleControl::OnEnumVerbs.md)|컨트롤의 동사를 열거 하는 컨테이너에 의해 호출 됩니다.|  
|[COleControl::OnEventAdvise](../Topic/COleControl::OnEventAdvise.md)|이벤트 처리기 연결에서 연결이 끊어진 경우 호출 됩니다.|  
|[COleControl::OnFontChanged](../Topic/COleControl::OnFontChanged.md)|스톡 글꼴 속성 변경 될 때 호출 됩니다.|  
|[COleControl::OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md)|주식 ForeColor 속성이 변경 될 때 호출 됩니다.|  
|[COleControl::OnFreezeEvents](../Topic/COleControl::OnFreezeEvents.md)|컨트롤의 이벤트 고정 또는 고정 취소 되 면 호출 됩니다.|  
|[COleControl::OnGetColorSet](../Topic/COleControl::OnGetColorSet.md)|알립니다 컨트롤은 `IOleObject::GetColorSet` 호출 된.|  
|[COleControl::OnGetControlInfo](../Topic/COleControl::OnGetControlInfo.md)|니모닉 정보 컨테이너를 제공합니다.|  
|[COleControl::OnGetDisplayString](../Topic/COleControl::OnGetDisplayString.md)|속성 값을 나타내는 문자열을 얻기 위해 호출 됩니다.|  
|[COleControl::OnGetInPlaceMenu](../Topic/COleControl::OnGetInPlaceMenu.md)|병합할 컨테이너 메뉴 컨트롤의 메뉴의 핸들을 요청 합니다.|  
|[COleControl::OnGetNaturalExtent](../Topic/COleControl::OnGetNaturalExtent.md)|검색 제안 된 크기와 범위 모드에 가장 가까운 컨트롤의 표시 크기를 재정의 합니다.|  
|[COleControl::OnGetPredefinedStrings](../Topic/COleControl::OnGetPredefinedStrings.md)|가능한 속성 값을 나타내는 문자열을 반환 합니다.|  
|[COleControl::OnGetPredefinedValue](../Topic/COleControl::OnGetPredefinedValue.md)|미리 정의 된 문자열에 해당 하는 값을 반환 합니다.|  
|[COleControl::OnGetViewExtent](../Topic/COleControl::OnGetViewExtent.md)|\(2 패스 그리기 사용 하려면 사용할 수 있습니다\) 컨트롤의 표시 영역의 크기를 검색 하려면 재정의 합니다.|  
|[COleControl::OnGetViewRect](../Topic/COleControl::OnGetViewRect.md)|특정 위치에서 시작 하는 사각형 컨트롤의 크기를 변환 하도록 재정의 하십시오.|  
|[COleControl::OnGetViewStatus](../Topic/COleControl::OnGetViewStatus.md)|검색할 컨트롤의 뷰 상태를 재정의 합니다.|  
|[COleControl::OnHideToolBars](../Topic/COleControl::OnHideToolBars.md)|컨트롤의 UI가 비활성화 되 면 컨테이너에 의해 호출 됩니다.|  
|[COleControl::OnInactiveMouseMove](../Topic/COleControl::OnInactiveMouseMove.md)|비활성 컨트롤에서 마우스 포인터 발송에 대 한 컨테이너를 무시 `WM_MOUSEMOVE` 메시지를 컨트롤 합니다.|  
|[COleControl::OnInactiveSetCursor](../Topic/COleControl::OnInactiveSetCursor.md)|비활성 컨트롤에서 마우스 포인터 발송에 대 한 컨테이너를 무시 `WM_SETCURSOR` 메시지를 컨트롤 합니다.|  
|[COleControl::OnKeyDownEvent](../Topic/COleControl::OnKeyDownEvent.md)|주식 KeyDown 이벤트가 발생 한 후에 호출 됩니다.|  
|[COleControl::OnKeyPressEvent](../Topic/COleControl::OnKeyPressEvent.md)|주식 KeyPress 이벤트가 발생 한 후에 호출 됩니다.|  
|[COleControl::OnKeyUpEvent](../Topic/COleControl::OnKeyUpEvent.md)|주식 KeyUp 이벤트가 발생 하면 호출 됩니다.|  
|[COleControl::OnMapPropertyToPage](../Topic/COleControl::OnMapPropertyToPage.md)|속성 편집에 사용할 수 있는 속성 페이지를 나타냅니다.|  
|[COleControl::OnMnemonic](../Topic/COleControl::OnMnemonic.md)|컨트롤의 니모닉 키를 누를 때 호출 됩니다.|  
|[COleControl::OnProperties](../Topic/COleControl::OnProperties.md)|컨트롤의 "속성" 동사를 호출 하면 호출 됩니다.|  
|[COleControl::OnQueryHitPoint](../Topic/COleControl::OnQueryHitPoint.md)|컨트롤의 표시는 해당된 시점 중복 여부 쿼리를 무시 합니다.|  
|[COleControl::OnQueryHitRect](../Topic/COleControl::OnQueryHitRect.md)|컨트롤의 표시는 지정 된 사각형에 중복 여부를 쿼리를 재정의 합니다.|  
|[COleControl::OnRenderData](../Topic/COleControl::OnRenderData.md)|지정 된 형식의 데이터를 검색 하는 프레임 워크에서 호출 합니다.|  
|[COleControl::OnRenderFileData](../Topic/COleControl::OnRenderFileData.md)|지정한 형식 파일에서 데이터를 검색 하는 프레임 워크에서 호출 합니다.|  
|[COleControl::OnRenderGlobalData](../Topic/COleControl::OnRenderGlobalData.md)|지정 된 형식의 전역 메모리에서 데이터를 검색 하는 프레임 워크에서 호출 합니다.|  
|[COleControl::OnResetState](../Topic/COleControl::OnResetState.md)|컨트롤의 속성을 기본값으로 다시 설정합니다.|  
|[COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md)|알립니다 컨트롤은 `IOleControl::SetClientSite` 호출 된.|  
|[COleControl::OnSetData](../Topic/COleControl::OnSetData.md)|컨트롤의 데이터를 다른 값으로 바꿉니다.|  
|[COleControl::OnSetExtent](../Topic/COleControl::OnSetExtent.md)|컨트롤의 범위에서 변경 된 후에 호출 됩니다.|  
|[COleControl::OnSetObjectRects](../Topic/COleControl::OnSetObjectRects.md)|컨트롤의 크기를 변경한 후에 호출 됩니다.|  
|[COleControl::OnShowToolBars](../Topic/COleControl::OnShowToolBars.md)|컨트롤의 UI 활성화 되었을 때 호출 됩니다.|  
|[COleControl::OnTextChanged](../Topic/COleControl::OnTextChanged.md)|스톡 텍스트 또는 캡션 속성 변경 될 때 호출 됩니다.|  
|[COleControl::OnWindowlessMessage](../Topic/COleControl::OnWindowlessMessage.md)|창 없는 컨트롤에 대 한 \(마우스 및 키보드 메시지\) 이외의 창 메시지를 처리합니다.|  
|[COleControl::ParentToClient](../Topic/COleControl::ParentToClient.md)|지점 컨트롤의 원점 기준으로 컨테이너의 원점 기준으로 점을 변환합니다.|  
|[COleControl::PostModalDialog](../Topic/COleControl::PostModalDialog.md)|모달 대화 상자가 닫힌 컨테이너에 알립니다.|  
|[COleControl::PreModalDialog](../Topic/COleControl::PreModalDialog.md)|모달 대화 상자에 표시 되는 컨테이너를 알립니다.|  
|[COleControl::RecreateControlWindow](../Topic/COleControl::RecreateControlWindow.md)|삭제 하 고 해당 컨트롤의 창이 다시 만듭니다.|  
|[COleControl::Refresh](../Topic/COleControl::Refresh.md)|컨트롤의 모양을 다시 그리기를 수행합니다.|  
|[COleControl::ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)|마우스 캡처를 해제 합니다.|  
|[COleControl::ReleaseDC](../Topic/COleControl::ReleaseDC.md)|컨테이너는 창 없는 컨트롤의 디스플레이 장치 컨텍스트를 해제합니다.|  
|[COleControl::ReparentControlWindow](../Topic/COleControl::ReparentControlWindow.md)|부모 창의 컨트롤을 다시 설정합니다.|  
|[COleControl::ResetStockProps](../Topic/COleControl::ResetStockProps.md)|초기화 `COleControl` 스톡 속성을 기본값으로 합니다.|  
|[COleControl::ResetVersion](../Topic/COleControl::ResetVersion.md)|버전 번호를 지정 된 값으로 초기화합니다.|  
|[COleControl::ScrollWindow](../Topic/COleControl::ScrollWindow.md)|창 없는 컨트롤을 영역 내 디스플레이 현재 위치에서 활성 이미지를 스크롤할 수 있습니다.|  
|[COleControl::SelectFontObject](../Topic/COleControl::SelectFontObject.md)|디바이스 컨텍스트에 사용자 지정 Font 속성을 선택합니다.|  
|[COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md)|스톡 Font 속성을 디바이스 컨텍스트로 선택합니다.|  
|[COleControl::SerializeExtent](../Topic/COleControl::SerializeExtent.md)|Serialize 하거나 디스플레이 공간 컨트롤을 초기화 합니다.|  
|[COleControl::SerializeStockProps](../Topic/COleControl::SerializeStockProps.md)|Serialize 하거나 초기화는 `COleControl` 스톡 속성입니다.|  
|[COleControl::SerializeVersion](../Topic/COleControl::SerializeVersion.md)|Serialize 하거나 컨트롤의 버전 정보를 초기화 합니다.|  
|[COleControl::SetAppearance](../Topic/COleControl::SetAppearance.md)|스톡 모양 속성의 값을 설정 합니다.|  
|[COleControl::SetBackColor](../Topic/COleControl::SetBackColor.md)|주식 BackColor 속성의 값을 설정 합니다.|  
|[COleControl::SetBorderStyle](../Topic/COleControl::SetBorderStyle.md)|주식 BorderStyle 속성의 값을 설정 합니다.|  
|[COleControl::SetCapture](../Topic/COleControl::SetCapture.md)|대신 컨트롤의 마우스 캡처를 소유 하기는 컨트롤의 컨테이너 창이 됩니다.|  
|[COleControl::SetControlSize](../Topic/COleControl::SetControlSize.md)|OLE 컨트롤의 크기와 위치를 설정합니다.|  
|[COleControl::SetEnabled](../Topic/COleControl::SetEnabled.md)|스톡 Enabled 속성의 값을 설정 합니다.|  
|[COleControl::SetFocus](../Topic/COleControl::SetFocus.md)|컨트롤의 컨테이너 창을 소유 입력된 포커스를 컨트롤 대신 사용 됩니다.|  
|[COleControl::SetFont](../Topic/COleControl::SetFont.md)|스톡 Font 속성의 값을 설정 합니다.|  
|[COleControl::SetForeColor](../Topic/COleControl::SetForeColor.md)|ForeColor 스톡 속성의 값을 설정 합니다.|  
|[COleControl::SetInitialSize](../Topic/COleControl::SetInitialSize.md)|먼저 컨테이너에 표시 될 때 OLE 컨트롤의 크기를 설정 합니다.|  
|[COleControl::SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md)|수정 된 컨트롤의 상태를 변경합니다.|  
|[COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)|편집 요청에 실패 했음을 나타냅니다.|  
|[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)|사용자가 컨트롤의 속성 값을 수정할 수 없습니다.|  
|[COleControl::SetRectInContainer](../Topic/COleControl::SetRectInContainer.md)|컨테이너를 기준으로 컨트롤의 사각형을 설정합니다.|  
|[COleControl::SetText](../Topic/COleControl::SetText.md)|스톡 텍스트 또는 캡션 속성의 값을 설정 합니다.|  
|[COleControl::ThrowError](../Topic/COleControl::ThrowError.md)|OLE 컨트롤에서 오류가 발생 하는 신호.|  
|[COleControl::TransformCoords](../Topic/COleControl::TransformCoords.md)|변환은 컨트롤 컨테이너 사이의 값을 조정합니다.|  
|[COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md)|변환 된  **OLE\_COLOR** 값은  **COLORREF** 값.|  
|[COleControl::WillAmbientsBeValidDuringLoad](../Topic/COleControl::WillAmbientsBeValidDuringLoad.md)|컨트롤이 로드 될 때 앰비언트 속성을 사용할 것인지 결정 합니다.|  
|[COleControl::WindowProc](../Topic/COleControl::WindowProc.md)|창 프로시저를 제공 된 `COleControl` 개체입니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleControl::DrawContent](../Topic/COleControl::DrawContent.md)|컨트롤의 모양을 업데이트 하는 경우 프레임 워크에서 호출 됩니다.|  
|[COleControl::DrawMetafile](../Topic/COleControl::DrawMetafile.md)|메타 파일 디바이스 컨텍스트 사용 될 때 프레임 워크에 의해 호출 됩니다.|  
|[COleControl::IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md)|자동화 메서드를 호출할을 수 있습니다.|  
|[COleControl::SetInitialDataFormats](../Topic/COleControl::SetInitialDataFormats.md)|컨트롤에서 지 원하는 데이터 형식 목록을 초기화 하는 프레임 워크에서 호출 합니다.|  
  
## 설명  
 파생 된 `CWnd`, Windows 창 개체의 모든 기능 및 이벤트 발생 및 메서드 및 속성을 지 원하는 것 같은 OLE에 특정 추가 기능이이 클래스를 상속 합니다.  
  
 OLE 컨트롤 OLE 컨테이너 응용 프로그램에 삽입할 수 및 양방향 시스템 이벤트 발생 및 노출을 메서드와 속성 컨테이너를 사용 하 여 컨테이너와 통신 합니다.  참고 표준 OLE 컨테이너는 OLE 컨트롤의 기본 기능을 지원 합니다.  OLE 컨트롤의 확장된 된 기능을 지원할 수는 없습니다.  컨테이너 컨트롤에서 수행 하는 특정 작업의 결과로 이벤트를 보낼 때 이벤트 발생을 발생 합니다.  결과적으로 컨테이너 컨트롤에는 노출 된 메서드 및 속성 집합을 멤버 함수와 유사 하 고 C\+\+ 클래스의 데이터 멤버를 사용 하 여 통신 합니다.  이 방법은 개발자가 컨트롤의 모양을 제어 하 여 특정 작업이 발생 하면 컨테이너를 알릴 수 있습니다.  
  
## 창 없는 컨트롤  
 OLE 컨트롤 창 없이 사용 되는 내부 활성화 될 수 있습니다.  창 없는 컨트롤에는 중요 한 이점이 있습니다.  
  
-   투명 한 사각형이 아닌 창 없는 컨트롤이 될 수 있습니다.  
  
-   창 없는 컨트롤 개체의 인스턴스 생성 및 크기 시간 줄이기  
  
 컨트롤 창이 필요 하지 않습니다.  단일 공유 창 \(일반적으로 컨테이너\) 및 약간의 디스패치 코드를 통해 쉽게 창을 제공 하는 서비스를 제공할 수 있습니다.  창을 만들면 불필요 한 복잡성 개체에는 대부분입니다.  
  
 창 없는 활성화를 사용 하는 경우 \(창이\) 컨테이너 컨트롤의 창에서 제공 된 서비스를 제공 하는 데 담당 합니다.  예를 들어, 컨트롤이 키보드 포커스를 쿼리하거나 마우스 캡처를 쿼리하거나 디바이스 컨텍스트를 가져와야 할 경우이 작업은 컨테이너에 의해 관리 됩니다.  `COleControl`[작업 창 없는 멤버 함수](http://msdn.microsoft.com/ko-kr/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) 컨테이너에서 이러한 작업을 호출 합니다.  
  
 창 없는 활성화를 사용 하면 메시지를 컨트롤의 컨테이너 대리자를 입력 `IOleInPlaceObjectWindowless` 인터페이스 \(확장명이  [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) 창 없는 지원\).  `COleControl`이 인터페이스의 구현을 조정 마우스를 적절 하 게 조정 된 후 이러한 컨트롤의 메시지 맵을 통해이 메시지 발송 됩니다.  메시지 맵에 해당 엔트리를 추가 하 여 이러한 메시지를 보통의 창 메시지 처럼 처리할 수 있습니다.  
  
 항상 사용할지는 창 없는 컨트롤에는 `COleControl` 대신 해당 멤버 함수 `CWnd` 해당 관련된 Windows API 함수 또는 멤버 함수.  
  
 OLE 컨트롤 개체가 활성화 되어 있지만 활성 비활성 전환에 필요한 작업 시간을 이동 하며 전환 속도 다운 때만 창을 만들 수도 있습니다.  경우가 문제입니다: 예를 들어, 텍스트 상자 격자가 고려.  때 열에서 커서 상하 각 컨트롤 활성화 및 비활성화 후 원위치 이어야 합니다.  비활성\/활성 전환 속도 직접 스크롤 속도 영향을 줍니다.  
  
 OLE 컨트롤 개발에 대 한 자세한 내용은 문서를 참조 하십시오.  [MFC 컨트롤을 ActiveX](../../mfc/mfc-activex-controls.md) 및  [개요: ActiveX MFC 컨트롤 프로그램을 만드는](../../mfc/reference/mfc-activex-control-wizard.md).  최적화 하 고 깜빡임 없는 창 없는 컨트롤을 포함 하 여 OLE 컨트롤 정보를 참조 하십시오.  [ActiveX MFC 컨트롤: 최적화](../../mfc/mfc-activex-controls-optimization.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `COleControl`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [MFC 샘플 CIRC3](../../top/visual-cpp-samples.md)   
 [TESTHELP MFC 샘플](../../top/visual-cpp-samples.md)   
 [COlePropertyPage Class](../../mfc/reference/colepropertypage-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)   
 [CPictureHolder Class](../../mfc/reference/cpictureholder-class.md)