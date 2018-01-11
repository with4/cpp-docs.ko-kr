---
title: "CMFCToolBarDateTimeCtrl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4f7bdc964da8df8d8a402ae70b38eec1dbbf436
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl 클래스
날짜 및 시간 선택 컨트롤을 포함 하는 도구 모음 단추입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|`CMFCToolBarDateTimeCtrl` 개체를 생성합니다.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|사용자 지정 하는 동안 사용자의 단추를 늘릴 수 있는지 여부를 지정 합니다. (재정의 [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|도구 모음 단추 속성은 현재 단추에 복사합니다. (재정의 [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|나중에 사용하기 위해 예약되어 있습니다.|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|도구 모음 단추에서 메뉴에 텍스트를 복사 합니다.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|첫 번째 검색 `CMFCToolBarDateTimeCtrl` 지정한 명령 id입니다. 응용 프로그램의 개체|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|날짜 및 시간 선택 컨트롤에 대 한 포인터를 반환합니다.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다. (재정의 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|날짜 및 시간 선택 컨트롤에서 선택한 시간을 가져오고에 지정 된 배치 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조입니다.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|지정한 명령 ID를 가집니다. 시간 선택 컨트롤 단추에서 선택한 시간을 반환 합니다.|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|사용자가 단추를 선택 하는 경우 단추의 테두리 표시 되는지 여부를 결정 합니다. (재정의 [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|단추를 처리 하는 지 여부를 지정 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다. (재정의 [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자. (재정의 [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|지정 된 장치 컨텍스트와 도킹 상태에 대 한 단추 크기를 계산 하기 위해 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|새 도구 모음에 단추를 삽입할 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|사용자가 컨트롤을 클릭할 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|부모 도구 모음에서 처리 될 때 프레임 워크에서 호출 된 `WM_CTLCOLOR` 메시지입니다. (재정의 [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|단추를 그리기 위해 프레임 워크에서 호출 된 **명령을** 의 창은 **사용자 지정** 대화 상자. (재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|전역 글꼴 변경 될 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|부모 도구 모음에서 이동 하면 프레임 워크에서 호출 합니다. (재정의 [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|프레임 워크에서 때 호출 단추 수 표시 하거나 숨깁니다. (재정의 [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|부모 도구 모음에서 해당 크기를 변경 합니다. 또는 위치 및 이러한 변경 하면 크기를 변경 하려면 단추가 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|부모 도구 모음에서 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|보관에서이 개체를 읽거나 보관 파일로 씁니다 (재정의 [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|도구 모음 단추 스타일을 설정합니다. (재정의 [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|시간 선택 컨트롤에서 날짜 및 시간을 설정합니다.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|지정한 명령 ID가 지정 되며 시간 선택 컨트롤의 모든 인스턴스에서 날짜 및 시간 설정|  
  
## <a name="remarks"></a>설명  
 날짜 및 시간 선택 컨트롤을 사용 하는 방법의 예를 들어 ToolbarDateTimePicker 샘플 프로젝트를 참조 하세요. 도구 모음 단추 컨트롤을 추가 하는 방법에 대 한 정보를 참조 하십시오. [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbardatetimectrl.h  
  
##  <a name="canbestretched"></a>CMFCToolBarDateTimeCtrl::CanBeStretched  
 사용자 지정 하는 동안 사용자의 단추를 늘릴 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 프레임 워크에는 사용자를 사용자 지정 하는 동안 도구 모음 단추를 늘이는 허용 되지 않습니다. 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) 하 여 사용자가 사용자 지정 하는 동안 도구 모음 단추를 날짜 및 시간을 늘릴 수 있도록 합니다.  
  
##  <a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl  
 만들고 초기화는 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) 개체입니다.  
  
```  
CMFCToolBarDateTimeCtrl(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=0,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 컨트롤 id입니다.  
  
 [in] `iImage`  
 도구 모음에 있는 이미지의 인덱스 `CMFCToolBarImages` 개체입니다.  
  
 [in] `dwStyle`  
 스타일은 `CMFCToolBarDateTimeCtrlImpl` 단추를 클릭할 때 생성 되는 창입니다.  
  
 [in] `iWidth`  
 컨트롤의 너비(픽셀)입니다.  
  
### <a name="remarks"></a>설명  
 이 개체는 시스템 날짜 및 시간으로 초기화 됩니다. 내부 창 스타일이 `CMFCToolBarDateTimeCtrlImpl` 개체에 포함 되어는 `dwStyle` 매개 변수 및 `WS_CHILD` 및 `WS_VISIBLE` 스타일입니다. 사용 하 여 이러한 스타일을 변경할 수 없습니다 `CMFCToolBarDateTimeCtrl::SetStyle`합니다. 사용 하 여 `SetStyle` 의 스타일을 변경 하는 `CMFCToolBarDateTimeCtrl` 제어 합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는의 개체를 생성 하는 `CMFCToolBarDateTimeCtrl` 클래스입니다. 이 코드 조각은의 일부인는 [날짜 시간 선택 도구 모음 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>CMFCToolBarDateTimeCtrl::CopyFrom  
 도구 모음 단추 속성은 현재 단추에 복사합니다.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `src`  
 복사할 소스 단추에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 도구 모음 단추를 도구 모음 단추 복사 하려면이 메서드를 호출 합니다. `src`형식 이어야 합니다 `CMFCToolBarDateTimeCtrl`합니다.  
  
##  <a name="exporttomenubutton"></a>CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 도구 모음 단추에서 메뉴에 텍스트를 복사 합니다.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `menuButton`  
 대상 메뉴 단추에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) 컨트롤의 명령 ID와 연결 된 문자열 리소스를 로드 하 여 합니다. 문자열 리소스에 대 한 자세한 내용은 참조 [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring)합니다.  
  
##  <a name="getbycmd"></a>CMFCToolBarDateTimeCtrl::GetByCmd  
 첫 번째 검색 `CMFCToolBarDateTimeCtrl` 지정한 명령 id입니다. 응용 프로그램의 개체  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 검색할 단추의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 `CMFCToolBarDateTimeCtrl` 지정한 명령 ID가 있는 응용 프로그램의 개체 또는 `NULL` 하지 않으면 `CMFCToolBarDateTimeCtrl` 개체는 지정한 명령 id입니다.  
  
### <a name="remarks"></a>설명  
 이 공유 유틸리티 메서드는 메서드에서 같은 [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) 및 [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) 가져오거나 시간의 모든 인스턴스는 날짜와 시간을 설정 하려면 지정한 명령 ID가 지정 되며 선택 컨트롤  
  
##  <a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 날짜 및 시간 선택 컨트롤에 대 한 포인터를 반환합니다.  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 날짜 및 시간 선택 컨트롤;에 대 한 포인터 또는 `NULL` 컨트롤이 존재 하지 않는 경우.  
  
### <a name="remarks"></a>설명  
 `CMFCToolBarDateTimeCtrl` 클래스를 초기화 하는 `m_pWndDateTime` 데이터 멤버를 삽입할 때는 `CMFCToolBarDateTimeCtrl` 도구 모음에는 개체입니다.  
  
##  <a name="gethwnd"></a>CMFCToolBarDateTimeCtrl::GetHwnd  
 도구 모음 단추와 연결 된 창 핸들을 검색 합니다.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>반환 값  
 날짜 및 시간 도구 모음 단추와 연결 된 창 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 재정의 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) 메서드.  
  
##  <a name="gettime"></a>CMFCToolBarDateTimeCtrl::GetTime  
 연결 된 날짜 및 시간 선택 컨트롤에서 선택한 시간을 가져오고에 지정 된 배치 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `[out] timeDest`  
 첫 번째 오버 로드에서는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 오버 로드에서는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.  
  
 `[out] pTimeDest`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조 시스템 시간 정보를 얻습니다. `NULL`이 아니어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 오버 로드 시간에 성공적으로 기록 하는 경우 0이 아닌는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체가 고, 그렇지 않으면 0입니다. 반환 값은 두 번째 및 세 번째 오버 로드에는 `DWORD` 에 설정 된 dwFlag 멤버 같거나는 [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) 구조입니다.  
  
### <a name="remarks"></a>설명  
 메서드는 [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) 구조체 멤버 dwFlags 날짜 및 시간 선택 날짜와 시간으로 설정 되었는지 여부를 나타냅니다. 컨트롤이 설정 된 값이 GDT_NONE, `no date` 상태, DTS_SHOWNONE 스타일을 사용 하 여 합니다. 반환 값 이면 GDT_VALID 시스템 시간 대상 위치에 성공적으로 저장 됩니다.  
  
##  <a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll  
 지정한 명령 ID를 가집니다. 시간 선택 컨트롤 단추에서 사용자가 선택한 시간을 반환  
  
```  
static BOOL GetTimeAll(
    UINT uiCmd,  
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeDest);
```  
  
### <a name="parameters"></a>매개 변수  
 `[in] uiCmd`  
 도구 모음 단추의 명령 ID를 지정 합니다.  
  
 `[out] timeDest`  
 첫 번째 오버 로드에서는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 오버 로드에서는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.  
  
 `[out] pTimeDest`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조 시스템 시간 정보를 얻습니다. `NULL`이 아니어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 프레임 워크 경우 명령 ID와 일치 하는 도구 모음 단추를 찾을 수 없습니다 `uiCmd`, 반환 값은 첫 번째 오버 로드에는 0이 되 고 다른 오버 로드에서 GDT_NONE 합니다. 반환 값은 호출에서 반환 값과 같을 경우 도구 모음 단추 발견 되 면 [CMFCToolBarDateTimeCtrl::GetTime](#gettime) 해당 단추입니다. 반환 값 0 또는 GDT_NONE 단추, 있으면 한다는 발생할 수 있습니다에 대 한 호출 `GetTime` 다른 이유로 유효한 날짜를 반환 하지 않았습니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 호출와 지정한 명령 ID가 할당 되는 도구 모음 단추에 찾습니다 [CMFCToolBarDateTimeCtrl::GetTime](#gettime) 해당 단추의 메서드.  
  
##  <a name="havehotborder"></a>CMFCToolBarDateTimeCtrl::HaveHotBorder  
 사용자가 단추를 선택 하는 경우 단추의 테두리 표시 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추를 선택 하는 경우의 테두리를 표시 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 컨트롤이 표시 되 면 0이 아닌 값을 반환 합니다.  
  
##  <a name="notifycommand"></a>CMFCToolBarDateTimeCtrl::NotifyCommand  
 단추를 처리 하는 지 여부를 지정 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iNotifyCode`  
 명령과 사용 하 여 연결 된 알림 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추를 처리 하는 경우는 `WM_COMMAND` 메시지 또는 `FALSE` 를 나타내는 부모 도구 모음에서 메시지를 처리 되어야 합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크를 보낼 때이 메서드를 호출는 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지를 부모 창입니다.  
  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) 처리 하 여는 [DTN_DATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761737) 알림입니다. 내부 시간 상태를 업데이트 하 고 모든 시간 속성이 업데이트 `CMFCToolBarDateTimeCtrl` 개체를 동일한 명령 id입니다.  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>설명  
 이 메서드가 기본 클래스 구현을 확장 [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), 의해 첫 번째 날짜에서 속성을 복사 및 시간에이 개체와 같은 명령 ID가 있는 모든 도구 모음에 컨트롤입니다. 도구 모음 제외에 날짜 및 시간 컨트롤이이 개체와 같은 명령 ID를 포함 하는 경우이 메서드는 아무 작업도 수행 합니다.  
  
 에 대 한 자세한 내용은 **사용자 지정** 대화 상자, 참조 [CMFCToolBarsCustomizeDialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)합니다.  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 새 도구 모음에 단추를 삽입할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 새 부모 창입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) 내부 다시 만들어 `CMFCToolBarDateTimeCtrlImpl` 개체입니다.  
  
##  <a name="onclick"></a>CMFCToolBarDateTimeCtrl::OnClick  
 사용자가 컨트롤을 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 사용되지 않습니다.  
  
 [in] `bDelay`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 단추 클릭 하 여 메시지를 처리 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), 경우에 0이 아닌 값을 반환 하 여 내부 `CMFCToolBarDateTimeCtrlImpl` 개체가 표시 됩니다.  
  
##  <a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl::OnCtlColor  
 부모 도구 모음에서 처리 될 때 프레임 워크에서 호출 된 `WM_CTLCOLOR` 메시지입니다.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `nCtlColor`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 단추의 배경을 칠하는 데 사용 하는 프레임 워크는 전역 브러시에 사용 되는 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor),으로 텍스트를 설정 및 전체 텍스트를 제공 된 장치 컨텍스트의 색 및 배경 색을 각각 백그라운드 합니다.  
  
 응용 프로그램에 사용할 수 있는 전역 옵션에 대 한 자세한 내용은 참조 [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)합니다.  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 전역 글꼴 변경 될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) 글로벌 글꼴의 컨트롤의 글꼴을 변경 하 여 합니다.  
  
 응용 프로그램에 사용할 수 있는 전역 옵션에 대 한 자세한 내용은 참조 [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)합니다.  
  
##  <a name="onmove"></a>CMFCToolBarDateTimeCtrl::OnMove  
 부모 도구 모음에서 이동 하면 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove))의 내부 위치를 업데이트 하 여 `CMFCToolBarDateTimeCtrlImpl` 개체입니다.  
  
##  <a name="onshow"></a>CMFCToolBarDateTimeCtrl::OnShow  
 프레임 워크에서 때 호출 단추 수 표시 하거나 숨깁니다.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 단추가 표시 되는지 여부를 지정 합니다. 이 매개 변수가 `TRUE`, 단추가 표시 됩니다. 그렇지 않으면 단추가 표시 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 하는 경우에 단추를 표시 하 여 `bShow` 은 `TRUE`합니다. 그렇지 않으면이 메서드는 단추를 숨깁니다.  
  
##  <a name="onsize"></a>CMFCToolBarDateTimeCtrl::OnSize  
 부모 도구 모음에서 해당 크기를 변경 합니다. 또는 위치 및 이러한 변경 하면 크기를 변경 하려면 단추가 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iSize`  
 새 너비 (픽셀)에서 단추입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) 크기와 내부 위치를 업데이트 하 여 `CMFCToolBarDateTimeCtrlImpl` 개체입니다.  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 부모 도구 모음에서 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 부모 창입니다.  
  
 [in] `iButtonIndex`  
 부모 단추 컬렉션에 있는 단추의 0부터 시작 하는 인덱스입니다.  
  
 [in] `wndToolTip`  
 도구 설명 텍스트를 표시 하는 컨트롤입니다.  
  
 [out] `str`  
 A `CString` 업데이트 된 도구 설명 텍스트를 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 도구 설명 텍스트; 업데이트 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) 단추와 연결 된 도구 설명 텍스트를 표시 하 여 합니다. 단추는 가로로 도킹 되지 않은 경우이 메서드는 아무 작업도 수행 하 고 반환 `FALSE`합니다.  
  
##  <a name="settime"></a>CMFCToolBarDateTimeCtrl::SetTime  
 시간 선택 컨트롤에서 날짜 및 시간을 설정합니다.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `[in] timeNew`  
 첫 번째 버전에 대 한 참조는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 컨트롤을 설정할 시간을 포함 하는 개체입니다. 두 번째 버전에 대 한 포인터는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤을 설정할 시간을 포함 하는 개체입니다.  
  
 `[in] pTimeNew`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 컨트롤을 설정할 시간을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 날짜 및 시간 선택 컨트롤에서 호출 하 여 시간을 설정 [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime)합니다.  
  
##  <a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll  
 지정한 명령 ID가 지정 되며 시간 선택 컨트롤의 모든 인스턴스에서 날짜 및 시간 설정  
  
```  
static BOOL SetTimeAll(
    UINT uiCmd,  
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `[in] uiCmd`  
 도구 모음 단추의 명령 ID를 지정 합니다.  
  
 `[in] timeNew`  
 첫 번째 버전에는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 컨트롤을 설정할 시간을 포함 하는 개체입니다. 두 번째 버전에 대 한 포인터는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤을 설정할 시간을 포함 하는 개체입니다.  
  
 `[in] pTimeNew`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 컨트롤을 설정할 시간을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정한 명령 ID 가진 도구 모음 단추를 찾아서 호출 하 여 날짜 및 시간 선택 컨트롤에서 시간을 설정 [CMFCToolBarDateTimeCtrl::SetTime](#settime)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)



