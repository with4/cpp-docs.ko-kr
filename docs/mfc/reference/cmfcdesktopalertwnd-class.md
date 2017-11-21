---
title: "CMFCDesktopAlertWnd 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
dev_langs: C++
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5e5927cf9697a25e7e6e76a3e71c3d41ba1b32ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
`CMFCDesktopAlertWnd` 클래스는 이벤트에 대 한 사용자에 게 화면에 나타나는 모덜리스 대화 상자의 기능을 구현 합니다.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>구문  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Cmfcdesktopalertwnd:: Create](#create)|만들고 바탕 화면 경고 창이 초기화 합니다.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|애니메이션 속도 반환합니다.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|애니메이션 형식을 반환합니다.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|자동 닫기 제한 시간을 반환합니다.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|캡션 높이 반환합니다.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|화면에서 바탕 화면 경고 창이의 마지막 유효한 위치를 반환합니다.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|투명도 수준을 반환합니다.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|작은 캡션을 사용 하 여 바탕 화면 경고 창이 표시 되는지 여부를 결정 합니다.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|바탕 화면 알림 메뉴에 있는 링크 단추를 클릭할 때 프레임 워크에서 호출 됩니다.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|자식 컨트롤에서 알림 메시지를 보낼 때 또는 액셀러레이터 키 번역 된 경우 사용자가 메뉴에서 항목을 선택 하는 경우 프레임 워크에서이 멤버 함수를 호출 합니다. (재정의 [CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|새 애니메이션 속도 설정합니다.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|애니메이션 유형을 설정합니다.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|자동 닫기 제한 시간을 설정합니다.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|작은 및 일반 캡션 간에 전환 합니다.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|투명도 수준을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 바탕 화면 경고 창이 투명 하 게 표시 하 고 애니메이션 효과 함께 나타날 수 있습니다 (지정 된 지연 후 또는 사용자가 닫기 단추를 클릭 하 여 닫을 때) 사라질 수 있습니다.  
  
 바탕 화면 경고 창이 아이콘, 메시지 텍스트 (레이블) 및 링크를 포함 하는 기본 대화 상자를 포함할 수도 있습니다. 또는 바탕 화면 경고 창이 응용 프로그램의 리소스에서 사용자 지정 대화 상자를 포함할 수 있습니다.  
  
 바탕 화면 경고 창이 두 단계에서 만듭니다. 먼저,을 만드는 생성자를 호출는 `CMFCDesktopAlertWnd` 개체입니다. 둘째, 호출 된 [cmfcdesktopalertwnd:: Create](#create) 창을 만들고에 연결 하는 멤버 함수는 `CMFCDesktopAlertWnd` 개체입니다.  
  
 `CMFCDesktopAlertWnd` 개체 바탕 화면 경고 창이의 클라이언트 영역을 채우는 특별 한 자식 대화 상자를 만듭니다. 대화 상자에 배치 하는 모든 컨트롤을 소유 합니다.  
  
 팝업 창에 사용자 지정 대화 상자를 표시 하려면 다음이 단계를 따르십시오.  
  
1.  `CMFCDesktopAlertDialog`에서 클래스를 파생합니다.  
  
2.  리소스에서 자식 대화 상자 템플릿을 만듭니다.  
  
3.  호출 [cmfcdesktopalertwnd:: Create](#create) 대화 상자 템플릿 및 파생된 클래스의 런타임 클래스 정보에 대 한 포인터의 리소스 ID를 사용 하 여 합니다.  
  
4.  호스트 컨트롤에서 생성 하는 모든 알림을 처리 하는 사용자 지정 대화 상자를 프로그래밍 하거나 이러한 알림을 직접 처리 하는 호스트 된 컨트롤을 프로그래밍 합니다.  
  
 바탕 화면 경고 창이 동작을 제어 하는 다음과 같은 기능을 사용 합니다.  
  
-   애니메이션 형식을 호출 하 여 설정 [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)합니다. 올바른 옵션에는 펼치려면 민 페이드 합니다.  
  
-   애니메이션 프레임 속도 호출 하 여 설정 [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)합니다.  
  
-   투명도 수준 호출 하 여 설정 [CMFCDesktopAlertWnd::SetTransparency](#settransparency)합니다.  
  
-   호출 하 여 캡션 크기를 작음으로 변경 [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)합니다. 작은 캡션은 높은 7 픽셀입니다.  
  
## <a name="example"></a>예제  
 다양 한 메서드를 사용 하는 방법을 보여 주는 다음 예제는 `CMFCDesktopAlertWnd` 구성 하는 클래스는 `CMFCDesktopAlertWnd` 개체입니다. 애니메이션 유형을 설정, 팝업 창의 투명도 설정 하 고, 작은 캡션 경고 창에 표시 되는지 지정 하 고 경고 창이 자동으로 닫힙니다. 되기 전 까지의 경과 시간을 설정 하는 방법을 보여 줍니다. 만들고 바탕 화면 경고 창이 초기화 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [바탕 화면 경고 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>Cmfcdesktopalertwnd:: Create  
 만들고 바탕 화면 경고 창이 초기화 합니다.  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pWndOwner`  
 경고 창의 소유자를 지정합니다. 해당 소유자는 바탕 화면 경고 창이 대 한 모든 알림을 받을 것입니다. 이 값은 `NULL`일 수 없습니다.  
  
 [in] `uiDlgResID`  
 경고 창의 리소스 ID를 지정합니다.  
  
 [in] `hMenu`  
 메뉴 단추를 클릭할 때 표시 되는 메뉴를 지정 합니다. 경우 `NULL`, 메뉴 단추가 표시 되지 않습니다.  
  
 [in] `ptPos`  
 화면 좌표를 사용 하 여, 경고 창이 표시 되는 초기 위치를 지정 합니다. 이 매개 변수 (-1,-1) 인 경우 화면의 오른쪽 아래 모서리에 경고 창이 표시 됩니다.  
  
 [in] `pRTIDlgBar`  
 경고 창의 클라이언트 영역에 설명 하는 사용자 지정 대화 상자 클래스에 대 한 런타임 클래스 정보입니다.  
  
 [in] `params`  
 경고 창을 만드는 데 사용 되는 매개 변수를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경고 창이 성공적으로 만들어진 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 경고 창을 만들도록이 메서드를 호출 합니다. 경고 창의 클라이언트 영역에는 사용자에 게 표시 되는 모든 컨트롤을 호스트 하는 자식 대화 상자가 포함 되어 있습니다.  
  
 첫 번째 메서드 오버 로드는 응용 프로그램의 리소스에서 로드 되는 자식 대화 상자가 포함 된 경고 창을 만듭니다. 첫 번째 메서드 오버 로드에 사용자 지정 대화 상자 클래스에 대 한 런타임 클래스 정보를 지정할 수도 있습니다.  
  
 두 번째 메서드 오버 로드에는 기본 컨트롤을 포함 하는 경고 창을 만듭니다. 컨트롤을 수정 하 여 표시를 지정할 수 있습니다는 [CMFCDesktopAlertWndInfo 클래스](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)합니다.  
  
##  <a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 애니메이션 속도 반환합니다.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경고 창 밀리초에서의 애니메이션 속도입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 속도 경고 창이 열리고 닫힙니다 속도 설명 합니다.  
  
##  <a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
 애니메이션 형식을 반환합니다.  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>반환 값  
 다음 애니메이션 유형 중 하나입니다.  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 자동 닫기 제한 시간을 반환합니다.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>반환 값  
 시간을 밀리초 단위로 지나면 경고 창이 자동으로 닫힙니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 경고 창이 자동으로 닫힙니다. 전에 남은 시간 경과 결정 합니다.  
  
##  <a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 캡션 높이 반환합니다.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 캡션 높이입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 파생된 클래스에서 재정의할 수 있습니다. 기본 구현 중 하나: 작은 캡션 또는 Windows API 함수에서 얻은 값 팝업 창이 표시 되는 경우 작은 캡션 높이 값 (7 픽셀)를 반환 `GetSystemMetrics(SM_CYSMCAPTION)`합니다.  
  
##  <a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 화면에서 바탕 화면 경고 창이의 마지막 위치를 반환합니다.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>반환 값  
 한 시점을 화면 좌표입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 화면에 경고 창의 마지막 유효한 위치를 반환합니다.  
  
##  <a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 투명도 수준을 반환합니다.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0에서 255 사이의 투명도 수준입니다. 값이 클수록, 불투명 창.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 경고 창이 현재 투명도 수준을 검색할 수 있습니다.  
  
##  <a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 작은 캡션 또는 보통 크기로 캡션 바탕 화면 경고 창이 있는지 여부를 결정 합니다.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`작은 캡션; 팝업 창이 표시 되는 경우 `FALSE` 보통 크기의 캡션을 사용 하 여 팝업 창이 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 작은 캡션 또는 보통 크기로 캡션 팝업 창에 있는지 확인 하려면이 메서드를 사용 합니다. 기본적으로 작은 캡션은 높은 7 픽셀입니다. Windows API 함수를 호출 하 여 보통 크기로 캡션의 높이 가져올 수 있습니다 `GetSystemMetrics(SM_CYCAPTION)`합니다.  
  
##  <a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  

  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CPoint&`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 바탕 화면 알림 메뉴에 있는 링크 단추를 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE`입니다.  
  
### <a name="remarks"></a>설명  
 파생된 클래스에서이 메서드를 재정의 하 여 알림 창에서 링크를 클릭할 때 알림을 받을 수 있습니다.  
  
##  <a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  

  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wParam`  
 [in] `lParam`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="remarks"></a>설명  
  
##  <a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  

  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hwnd`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 새 애니메이션 속도 설정합니다.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nSpeed`  
 새 애니메이션 속도 밀리초 단위로 지정합니다.  
  
### <a name="remarks"></a>설명  
 경고 창에 대 한 애니메이션 속도 설정 하려면이 메서드를 호출 합니다. 기본 애니메이션 속도 30 밀리초입니다.  
  
##  <a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
 애니메이션 유형을 설정합니다.  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `type`  
 애니메이션 유형을 지정합니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 형식을 설정 하려면이 메서드를 호출 합니다. 다음 값 중 하나를 지정할 수 있습니다.  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 자동 닫기 제한 시간을 설정합니다.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTime`  
 시간을 밀리초 단위로 하 경과할 때까지 경고 창이 자동으로 닫힙니다.  
  
### <a name="remarks"></a>설명  
 사용자는 창 상호 작용 하지 하는 경우 지정된 된 시간 이후에 경고 창이 자동으로 닫혀 있습니다.  
  
##  <a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 캡션 작고 보통 크기로 전환 합니다.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSmallCaption`  
 `TRUE`작은 캡션; 알림 창에 표시 되는지 지정 하려면 그렇지 않으면 `FALSE` 경고 창이 보통 크기로 캡션이 표시 되는지 지정 하려면.  
  
### <a name="remarks"></a>설명  
 소형 또는 보통 크기로 캡션을 표시 하려면이 메서드를 호출 합니다. 기본적으로 작은 캡션은 높은 7 픽셀입니다. Windows API 함수를 호출 하 여 일반 캡션의 크기를 가져올 수 있습니다 `GetSystemMetrics(SM_CYCAPTION)`합니다.  
  
##  <a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 팝업 창의 투명도 수준을 설정합니다.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTransparency`  
 투명도 수준을 지정합니다. 이 값은 0에서 255 사이 여야 합니다. 값이 클수록, 불투명 창.  
  
### <a name="remarks"></a>설명  
 팝업 창의 투명도 수준을 설정 하려면이 함수를 호출 합니다.  
  
##  <a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  

  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo 클래스](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)
