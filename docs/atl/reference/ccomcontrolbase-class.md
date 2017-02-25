---
title: "CComControlBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComControlBase"
  - "ATL.CComControlBase"
  - "ATL::CComControlBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComControlBase class"
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComControlBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 만들기 및 ATL 컨트롤을 관리 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class ATL_NO_VTABLE CComControlBase  
  
```  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CComControlBase::AppearanceType](../Topic/CComControlBase::AppearanceType.md)|재정의 하는 경우에 `m_nAppearance` 스톡 속성이 없는 유형의 `short`.|  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComControlBase::CComControlBase](../Topic/CComControlBase::CComControlBase.md)|생성자입니다.|  
|[CComControlBase::~CComControlBase](../Topic/CComControlBase::~CComControlBase.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComControlBase::ControlQueryInterface](../Topic/CComControlBase::ControlQueryInterface.md)|요청 된 인터페이스에 대 한 포인터를 검색합니다.|  
|[CComControlBase::DoesVerbActivate](../Topic/CComControlBase::DoesVerbActivate.md)|확인 하는 `iVerb` 매개 변수 사용 `IOleObjectImpl::DoVerb` 하나는 컨트롤의 사용자 인터페이스를 활성화 \(`iVerb` 같음 `OLEIVERB_UIACTIVATE`\), 컨트롤을 두 번 클릭할 때 수행할 동작을 정의 \(`iVerb` 같음 `OLEIVERB_PRIMARY`\), 컨트롤 표시 \(`iVerb` 같음 `OLEIVERB_SHOW`\), 또는 컨트롤을 활성화 \(`iVerb` 같음  **OLEIVERB\_INPLACEACTIVATE**\).|  
|[CComControlBase::DoesVerbUIActivate](../Topic/CComControlBase::DoesVerbUIActivate.md)|확인 하는 `iVerb` 매개 변수 사용 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하 고 반환  **TRUE**.|  
|[CComControlBase::DoVerbProperties](../Topic/CComControlBase::DoVerbProperties.md)|컨트롤의 속성 페이지를 표시합니다.|  
|[CComControlBase::FireViewChange](../Topic/CComControlBase::FireViewChange.md)|컨테이너에 컨트롤을 다시 그리도록 지시 하려면이 메서드를 호출 하거나 컨트롤의 보기 변경 되었음을 등록 된 advise 싱크에 알릴지.|  
|[CComControlBase::GetAmbientAppearance](../Topic/CComControlBase::GetAmbientAppearance.md)|검색  **DISPID\_AMBIENT\_APPEARANCE**, 현재 컨트롤에 대 한 설정 모양: 평면 및 3d에 대 한 1 0.|  
|[CComControlBase::GetAmbientAutoClip](../Topic/CComControlBase::GetAmbientAutoClip.md)|검색  **DISPID\_AMBIENT\_AUTOCLIP**, 컨테이너의 표시 영역 컨트롤의 자동 클리핑을 지원 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientBackColor](../Topic/CComControlBase::GetAmbientBackColor.md)|검색  **DISPID\_AMBIENT\_BACKCOLOR**, 컨테이너에 의해 정의 된 모든 컨트롤의 앰비언트 배경색입니다.|  
|[CComControlBase::GetAmbientCharSet](../Topic/CComControlBase::GetAmbientCharSet.md)|검색  **DISPID\_AMBIENT\_CHARSET**, 컨테이너에 의해 정의 된 모든 컨트롤에 앰비언트 문자 집합입니다.|  
|[CComControlBase::GetAmbientCodePage](../Topic/CComControlBase::GetAmbientCodePage.md)|검색  **DISPID\_AMBIENT\_CODEPAGE**, 컨테이너에 의해 정의 된 모든 컨트롤에 앰비언트 문자 집합입니다.|  
|[CComControlBase::GetAmbientDisplayAsDefault](../Topic/CComControlBase::GetAmbientDisplayAsDefault.md)|검색  **DISPID\_AMBIENT\_DISPLAYASDEFAULT**, 플래그는  **TRUE** 컨테이너 컨트롤에 기본 단추를이 사이트에 표시 되 고 따라서 단추 컨트롤에 두꺼운 프레임이 자신 합니다 경우.|  
|[CComControlBase::GetAmbientDisplayName](../Topic/CComControlBase::GetAmbientDisplayName.md)|검색  **DISPID\_AMBIENT\_DISPLAYNAME**를 컨테이너 컨트롤에 제공 된 이름입니다.|  
|[CComControlBase::GetAmbientFont](../Topic/CComControlBase::GetAmbientFont.md)|검색에 대 한 포인터의 컨테이너의 앰비언트 `IFont` 인터페이스.|  
|[CComControlBase::GetAmbientFontDisp](../Topic/CComControlBase::GetAmbientFontDisp.md)|검색에 대 한 포인터의 컨테이너의 앰비언트  **IFontDisp** 디스패치 인터페이스입니다.|  
|[CComControlBase::GetAmbientForeColor](../Topic/CComControlBase::GetAmbientForeColor.md)|검색  **DISPID\_AMBIENT\_FORECOLOR**, 컨테이너에서 정의 된 모든 컨트롤의 앰비언트 전경색입니다.|  
|[CComControlBase::GetAmbientLocaleID](../Topic/CComControlBase::GetAmbientLocaleID.md)|검색  **DISPID\_AMBIENT\_LOCALEID**, 컨테이너에서 사용 되는 언어 식별자입니다.|  
|[CComControlBase::GetAmbientMessageReflect](../Topic/CComControlBase::GetAmbientMessageReflect.md)|검색  **DISPID\_AMBIENT\_MESSAGEREFLECT**, 컨테이너 창 메시지를 받을지 여부를 나타내는 플래그 \(예: `WM_DRAWITEM`\) 이벤트로.|  
|[CComControlBase::GetAmbientPalette](../Topic/CComControlBase::GetAmbientPalette.md)|검색  **DISPID\_AMBIENT\_PALETTE**, 사용 하는 컨테이너에 액세스 하는 `HPALETTE`.|  
|[CComControlBase::GetAmbientProperty](../Topic/CComControlBase::GetAmbientProperty.md)|지정 된 컨테이너 속성 검색 `id`.|  
|[CComControlBase::GetAmbientRightToLeft](../Topic/CComControlBase::GetAmbientRightToLeft.md)|검색  **DISPID\_AMBIENT\_RIGHTTOLEFT**, 콘텐츠 컨테이너에서 표시 되는 방향입니다.|  
|[CComControlBase::GetAmbientScaleUnits](../Topic/CComControlBase::GetAmbientScaleUnits.md)|검색  **DISPID\_AMBIENT\_SCALEUNITS**, 표시 레이블을 지정 하기 위한 컨테이너의 앰비언트 단위 \(예: 인치 또는 센티미터\).|  
|[CComControlBase::GetAmbientShowGrabHandles](../Topic/CComControlBase::GetAmbientShowGrabHandles.md)|검색  **DISPID\_AMBIENT\_SHOWGRABHANDLES**, 컨테이너 컨트롤 잡기 핸들에 대 한 자체 활성 상태인 경우 표시할 수 있는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientShowHatching](../Topic/CComControlBase::GetAmbientShowHatching.md)|검색  **DISPID\_AMBIENT\_SHOWHATCHING**, 컨테이너 컨트롤 UI 활성 상태일 때 자체 빗살된 무늬로 표시 허용 되는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientSupportsMnemonics](../Topic/CComControlBase::GetAmbientSupportsMnemonics.md)|검색  **DISPID\_AMBIENT\_SUPPORTSMNEMONICS**, 컨테이너 키보드 니모닉을 지원 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientTextAlign](../Topic/CComControlBase::GetAmbientTextAlign.md)|검색  **DISPID\_AMBIENT\_TEXTALIGN**, 컨테이너에서 지 원하는 기본 텍스트 맞춤: 0 \(숫자, 텍스트 왼쪽\) 일반 맞춤, 왼쪽 맞춤 1, 2 가운데 맞춤 및 오른쪽 맞춤에 대해 3.|  
|[CComControlBase::GetAmbientTopToBottom](../Topic/CComControlBase::GetAmbientTopToBottom.md)|검색  **DISPID\_AMBIENT\_TOPTOBOTTOM**, 콘텐츠 컨테이너에서 표시 되는 방향입니다.|  
|[CComControlBase::GetAmbientUIDead](../Topic/CComControlBase::GetAmbientUIDead.md)|검색  **DISPID\_AMBIENT\_UIDEAD**, 컨테이너 사용자 인터페이스 작업에 응답 하는 컨트롤을 원하는 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientUserMode](../Topic/CComControlBase::GetAmbientUserMode.md)|검색  **DISPID\_AMBIENT\_USERMODE**, 컨테이너에서 실행 모드 인지 여부를 나타내는 플래그 \(**TRUE**\) 또는 디자인 모드 \(**거짓**\).|  
|[CComControlBase::GetDirty](../Topic/CComControlBase::GetDirty.md)|데이터 멤버의 값을 반환 합니다. `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](../Topic/CComControlBase::GetZoomInfo.md)|검색 된 x 및 y 값의 분자와 분모의 확대\/축소 비율 컨트롤 활성화에 대 한 전체 편집.|  
|[CComControlBase::InPlaceActivate](../Topic/CComControlBase::InPlaceActivate.md)|어떤 동사에 상태를 비활성 상태에서 전환 하면 컨트롤이 `iVerb` 를 나타냅니다.|  
|[CComControlBase::InternalGetSite](../Topic/CComControlBase::InternalGetSite.md)|컨트롤 사이트 식별 된 인터페이스에 대 한 포인터를 쿼리 하는이 메서드를 호출 합니다.|  
|[CComControlBase::OnDraw](../Topic/CComControlBase::OnDraw.md)|컨트롤을 그리도록이 메서드를 재정의 합니다.|  
|[CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)|기본  **OnDrawAdvanced**  드로잉에 대 한 정규화 된 장치 컨텍스트를 준비 하 고 호출 컨트롤 클래스의 `OnDraw` 메서드.|  
|[CComControlBase::OnKillFocus](../Topic/CComControlBase::OnKillFocus.md)|컨트롤의 사용 기간 현재 위치에서 활성화 되 고 유효한 컨트롤 사이트에서 다음 컨테이너 컨트롤이 포커스를 벗어났음을 알립니다 확인 합니다.|  
|[CComControlBase::OnMouseActivate](../Topic/CComControlBase::OnMouseActivate.md)|UI는 사용자 모드에서 다음 컨트롤을 활성화를 확인 합니다.|  
|[CComControlBase::OnPaint](../Topic/CComControlBase::OnPaint.md)|페인팅에 대 한 컨테이너를 준비 하 고 컨트롤의 클라이언트 영역을 가져옵니다 다음 컨트롤 클래스를 호출 `OnDraw` 메서드.|  
|[CComControlBase::OnSetFocus](../Topic/CComControlBase::OnSetFocus.md)|컨트롤의 사용 기간 현재 위치에서 활성화 되 고 유효한 컨트롤 사이트에서 다음 컨트롤 컨테이너에 알립니다 검사 포커스를 확보 했습니다.|  
|[CComControlBase::PreTranslateAccelerator](../Topic/CComControlBase::PreTranslateAccelerator.md)|자신의 키보드 가속기 처리기를 제공 하려면이 메서드를 재정의 합니다.|  
|[CComControlBase::SendOnClose](../Topic/CComControlBase::SendOnClose.md)|컨트롤이 닫 혔 음 advise 소유자에 등록 된 모든 advise 싱크에 알립니다.|  
|[CComControlBase::SendOnDataChange](../Topic/CComControlBase::SendOnDataChange.md)|컨트롤 데이터를 변경한 advise 소유자와 등록 된 모든 advise 싱크에 알립니다.|  
|[CComControlBase::SendOnRename](../Topic/CComControlBase::SendOnRename.md)|새 모니커 권한이 advise 소유자에 등록 된 모든 advise 싱크에 알립니다.|  
|[CComControlBase::SendOnSave](../Topic/CComControlBase::SendOnSave.md)|컨트롤이 저장 된 advise 소유자에 등록 된 모든 advise 싱크에 알립니다.|  
|[CComControlBase::SendOnViewChange](../Topic/CComControlBase::SendOnViewChange.md)|등록 된 모든 advise 싱크에 컨트롤의 보기 변경 알립니다.|  
|[CComControlBase::SetControlFocus](../Topic/CComControlBase::SetControlFocus.md)|설정 하거나 컨트롤에서 키보드 포커스를 제거 합니다.|  
|[CComControlBase::SetDirty](../Topic/CComControlBase::SetDirty.md)|데이터 멤버를 설정 합니다. `m_bRequiresSave` 에 `bDirty`.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CComControlBase::m\_bAutoSize](../Topic/CComControlBase::m_bAutoSize.md)|컨트롤은 모든 다른 크기 수 없습니다 나타내는 플래그입니다.|  
|[CComControlBase::m\_bDrawFromNatural](../Topic/CComControlBase::m_bDrawFromNatural.md)|임을 나타내는 플래그 `IDataObjectImpl::GetData` 및 `CComControlBase::GetZoomInfo` 에서 컨트롤 크기를 설정 해야 `m_sizeNatural` 가 아닌 `m_sizeExtent`.|  
|[CComControlBase::m\_bDrawGetDataInHimetric](../Topic/CComControlBase::m_bDrawGetDataInHimetric.md)|임을 나타내는 플래그 `IDataObjectImpl::GetData` HIMETRIC 단위, 않습니다 픽셀을 그릴 때 사용 해야 합니다.|  
|[CComControlBase::m\_bInPlaceActive](../Topic/CComControlBase::m_bInPlaceActive.md)|현재 위치에서 활성화 컨트롤 인지를 나타내는 플래그입니다.|  
|[CComControlBase::m\_bInPlaceSiteEx](../Topic/CComControlBase::m_bInPlaceSiteEx.md)|컨테이너 지원 나타내는 플래그는  **IOleInPlaceSiteEx** 인터페이스 및 OCX96 하 고 깜빡임 없는 창 없는 컨트롤과 같은 기능을 제어 합니다.|  
|[CComControlBase::m\_bNegotiatedWnd](../Topic/CComControlBase::m_bNegotiatedWnd.md)|컨트롤 컨테이너 지원 \(예: 깜빡임 없는 및 창 없는 컨트롤\), OCX96 제어 기능에 대 한 협상 했습니다 여부 및 창 또는 창 없는 컨트롤 인지를 나타내는 플래그입니다.|  
|[CComControlBase::m\_bRecomposeOnResize](../Topic/CComControlBase::m_bRecomposeOnResize.md)|컨트롤 컨테이너 컨트롤의 표시 크기가 변경 될 때 해당 프레젠테이션의 재구성 하려는 나타내는 플래그입니다.|  
|[CComControlBase::m\_bRequiresSave](../Topic/CComControlBase::m_bRequiresSave.md)|마지막으로 저장 된 컨트롤이 변경 되었음을 나타내는 플래그입니다.|  
|[CComControlBase::m\_bResizeNatural](../Topic/CComControlBase::m_bResizeNatural.md)|컨트롤 원하는 크기의 자연 스러운 정도 \(실제 크기 실제 크기\)를 나타내는 플래그 컨테이너 컨트롤의 표시 크기를 변경할 때.|  
|[CComControlBase::m\_bUIActive](../Topic/CComControlBase::m_bUIActive.md)|메뉴 및 도구 모음과 같은 컨트롤의 사용자 인터페이스를 나타내는 플래그가 활성화 됩니다.|  
|[CComControlBase::m\_bUsingWindowRgn](../Topic/CComControlBase::m_bUsingWindowRgn.md)|컨트롤 컨테이너에서 제공 하는 창 영역을 사용 하 고 나타내는 플래그입니다.|  
|[CComControlBase::m\_bWasOnceWindowless](../Topic/CComControlBase::m_bWasOnceWindowless.md)|컨트롤, 창 없는 되었습니다 여부 이제 창 없는 않을 나타내는 플래그입니다.|  
|[CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md)|컨테이너가 창 없는 컨트롤을 지 원하는 경우에 컨트롤을 창 있는 여야 합니다 나타내는 플래그입니다.|  
|[CComControlBase::m\_bWndLess](../Topic/CComControlBase::m_bWndLess.md)|창 없는 컨트롤을 나타내는 플래그입니다.|  
|[CComControlBase::m\_hWndCD](../Topic/CComControlBase::m_hWndCD.md)|컨트롤과 연결 된 창 핸들에 대 한 참조가 포함 되어 있습니다.|  
|[CComControlBase::m\_nFreezeEvents](../Topic/CComControlBase::m_nFreezeEvents.md)|개수는 컨테이너 이벤트 \(이벤트 허용 거부\) \(수용 이벤트의\) 이벤트는 중간 해제 하지 않고 고정 한 횟수입니다.|  
|[CComControlBase::m\_rcPos](../Topic/CComControlBase::m_rcPos.md)|컨테이너 좌표로 표시 하는 컨트롤의 픽셀에서 위치입니다.|  
|[CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md)|\(각 단위 0.01 밀리미터\)이 메트릭 단위는 특정 디스플레이 대 한 컨트롤의 범위입니다.|  
|[CComControlBase::m\_sizeNatural](../Topic/CComControlBase::m_sizeNatural.md)|\(각 단위 0.01 밀리미터\)이 메트릭 단위에서 컨트롤의 실제 크기입니다.|  
|[CComControlBase::m\_spAdviseSink](../Topic/CComControlBase::m_spAdviseSink.md)|Advise 연결 컨테이너에 대 한 직접적인 포인터 \(컨테이너의  [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)\).|  
|[CComControlBase::m\_spAmbientDispatch](../Topic/CComControlBase::m_spAmbientDispatch.md)|A `CComDispatchDriver` 개체를 검색 하 고 해당 컨테이너의 속성을 통해 설정할 수 있는 `IDispatch` 포인터.|  
|[CComControlBase::m\_spClientSite](../Topic/CComControlBase::m_spClientSite.md)|컨테이너 내에서 컨트롤의 클라이언트 사이트에 대 한 포인터입니다.|  
|[CComControlBase::m\_spDataAdviseHolder](../Topic/CComControlBase::m_spDataAdviseHolder.md)|어드바이스 데이터 개체 간에 advise 연결을 저장 하는 표준 방법을 제공 합니다.|  
|[CComControlBase::m\_spInPlaceSite](../Topic/CComControlBase::m_spInPlaceSite.md)|컨테이너에 대 한 포인터  [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586),  [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), 또는  [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) 인터페이스 포인터입니다.|  
|[CComControlBase::m\_spOleAdviseHolder](../Topic/CComControlBase::m_spOleAdviseHolder.md)|Advise 연결을 저장 하는 방법의 표준 구현을 제공 합니다.|  
  
## 설명  
 이 클래스는 만들기 및 ATL 컨트롤을 관리 하는 방법을 제공 합니다.  [CComControl 클래스](../../atl/reference/ccomcontrol-class.md) 에서 파생 된 `CComControlBase`.  ATL 컨트롤 마법사를 사용 하 여 표준 컨트롤 또는 DHTML 컨트롤을 만들 때 마법사는 자동으로 클래스에서 파생 됩니다 `CComControlBase`.  
  
 컨트롤 만들기에 대 한 자세한 내용은  [ATL 자습서](../../atl/active-template-library-atl-tutorial.md).  ATL 프로젝트 마법사에 대 한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md).  
  
## 요구 사항  
 **헤더:** atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)