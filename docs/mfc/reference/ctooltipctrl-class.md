---
title: CToolTipCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9436f3809a337b732a2e95d9c30b9baa45c4e8ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123112"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
응용 프로그램 도구의 용도를 설명하는 텍스트 한 줄을 표시하는 작은 팝업 창인 "도구 설명 컨트롤"의 기능을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|활성화 및 도구 설명 컨트롤을 비활성화 합니다.|  
|[CToolTipCtrl::AddTool](#addtool)|도구 설명 컨트롤을 도구를 등록합니다.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|도구 설명 컨트롤의 텍스트 간의 변환 사각형 및 해당 창의 사각형을 표시합니다.|  
|[CToolTipCtrl::Create](#create)|도구 설명 컨트롤을 만들고에 연결 된 `CToolTipCtrl` 개체입니다.|  
|[CToolTipCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 도구 설명 컨트롤을 만들고에 연결 된 `CToolTipCtrl` 개체입니다.|  
|[CToolTipCtrl::DelTool](#deltool)|도구 설명 컨트롤에서 도구를 제거합니다.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|도구 설명의 크기를 검색 합니다.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|현재 도구 설명 컨트롤이 표시 하는 도구 설명 창의 텍스트, 위치, 크기 등의 정보를 검색 합니다.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|초기, 팝업 및 reshow를 검색 하는 도구에 대 한 현재 설정 되어 있는 기간 설명 컨트롤입니다.|  
|[CToolTipCtrl::GetMargin](#getmargin)|위쪽, 왼쪽, 아래쪽 및 오른쪽 여백이 도구 설명 창이 대해 설정 된 검색 합니다.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|도구 설명 창이 대 한 최대 너비를 검색합니다.|  
|[CToolTipCtrl::GetText](#gettext)|도구 설명 컨트롤을 도구에 대 한 유지 관리 하는 텍스트를 검색 합니다.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|도구 설명 창의 배경색을 검색합니다.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|도구 설명 창이의 텍스트 색을 검색합니다.|  
|[CToolTipCtrl::GetTitle](#gettitle)|현재 도구 설명 컨트롤의 제목을 검색합니다.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|도구 설명 컨트롤에서 유지 관리 도구 수를 검색 합니다.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|도구 설명 컨트롤 유지 관리 하는 도구에 대 한 정보를 검색 합니다.|  
|[CToolTipCtrl::HitTest](#hittest)|지정 된 도구의 경계 사각형 내의 인지 확인 하는 지점을 테스트 합니다. 이 경우이 도구에 대 한 정보를 검색 합니다.|  
|[CToolTipCtrl::Pop](#pop)|보기에서 표시 된 도구 설명 창이 제거합니다.|  
|[CToolTipCtrl::Popup](#popup)|마지막 마우스 메시지가 좌표에 표시 하려면 현재 도구 설명 컨트롤을 하면 됩니다.|  
|[CToolTipCtrl::RelayEvent](#relayevent)|처리에 대 한 도구 설명 컨트롤에 마우스 메시지가 전달합니다.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|팝업, 초기 설정 하 고 도구 설명 컨트롤에 대 한 기간 reshow 합니다.|  
|[CToolTipCtrl::SetMargin](#setmargin)|위쪽, 왼쪽, 아래쪽 및 오른쪽 여백이 도구 설명 창이 대 한 설정합니다.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|도구 설명 창이 대 한 최대 너비를 설정합니다.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|도구 설명 창이에서 명령 프롬프트 창의 배경색을 설정합니다.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|도구 설명 창이의 텍스트 색을 설정합니다.|  
|[CToolTipCtrl::SetTitle](#settitle)|도구 설명에 아이콘 및 제목을 표준 문자열을 추가합니다.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|도구 설명 하는 도구에 대 한 유지 관리 하는 정보를 설정 합니다.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|도구에 대 한 새로운 경계 사각형을 설정합니다.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|도구 설명 창이의 비주얼 스타일을 설정합니다.|  
|[CToolTipCtrl::Update](#update)|현재 도구 다시 그릴를 강제로 수행 합니다.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|도구에 대 한 도구 설명 텍스트를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 "도구"는 자식 창 또는 컨트롤 창의 클라이언트 영역 내에서 응용 프로그램 정의 된 사각형 영역 등과 같이 한 창 중 하나입니다. 도구 설명에는 대부분의 사용자는 도구에 커서를 놓습니다 있고 그대로 있을 약 절반에 대 한 두 번째 경우에 표시 되는 시간 숨겨져 있습니다. 도구 설명 커서 옆에 표시 하 고 사용자가 마우스 단추를 클릭 하거나 커서 도구 밖으로 이동 하면 사라집니다.  
  
 `CToolTipCtrl` 도구 설명 텍스트, 도구 설명 창이 자체의 너비 및 도구 설명의 배경색과 텍스트 색 주위의 여백 너비는 초기 시간 및 기간은 도구 설명의 제어 기능을 제공 합니다. 단일 도구 설명 컨트롤 둘 이상의 도구에 대 한 정보를 제공할 수 있습니다.  
  
 `CToolTipCtrl` 클래스 Windows 공통 도구 설명 컨트롤의 기능을 제공 합니다. 이 컨트롤 (및 따라서는 `CToolTipCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수는 있습니다.  
  
 도구 설명을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 [CFrameWnd에서 파생 되지 않은 Windows에 도구 설명](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CToolTipCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [를 사용 하 여 CToolTipCtrl](../../mfc/using-ctooltipctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="activate"></a>  CToolTipCtrl::Activate  
 이 기능을 활성화 또는 비활성화 도구 설명 컨트롤을 호출 합니다.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 *bActivate*  
 도구 설명 컨트롤이 활성화 되거나 비활성화 되려고를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 경우 *bActivate* 가 TRUE 이면 컨트롤이 활성화 되; FALSE 인 경우 비활성화 됩니다.  
  
 컨트롤;에 등록 하는 도구에 커서를 가져갈 때 도구 설명 정보 표시 도구 설명 컨트롤이 활성화 되 면 활성 상태인 도구 설명 정보 나타나지 않습니다, 심지어 커서가 있는 경우에 도구입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
##  <a name="addtool"></a>  CToolTipCtrl::AddTool  
 도구 설명 컨트롤을 도구를 등록합니다.  
  
```  
BOOL AddTool(
    CWnd* pWnd,  
    UINT nIDText,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);

 
BOOL AddTool(
    CWnd* pWnd,  
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *nIDText*  
 이 도구에 대 한 텍스트를 포함 하는 문자열 리소스의 ID입니다.  
  
 *lpRectTool*  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 도구의 좌표가 포함 된 구조체의 경계 사각형입니다. 로 식별 되는 창의 클라이언트 영역의 왼쪽 위 모퉁이 기준으로 좌표는 *pWnd*합니다.  
  
 *nIDTool*  
 ID는 도구입니다.  
  
 *lpszText*  
 이 도구에 대 한 텍스트에 대 한 포인터입니다. 이 매개 변수 LPSTR_TEXTCALLBACK 값이 포함 된 TTN_NEEDTEXT 알림 메시지 창의 부모로 이동 하는 *pWnd* 를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 *lpRectTool* 및 *nIDTool* 매개 변수는 둘 다 유효 해야 경우 *lpRectTool* 이 NULL 이면 *nIDTool* 0 이어야 합니다.  
  
 도구 설명 컨트롤은 여러 도구와 연결할 수 있습니다. 도구에 커서를 가져갈 때 도구 설명에 저장 된 정보가 표시 되도록 도구 설명 컨트롤에는 도구를 등록 하려면이 함수를 호출 합니다.  
  
> [!NOTE]
>  사용 하 여 정적 컨트롤 도구 설명을 설정할 수 없습니다 `AddTool`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect  
 도구 설명 컨트롤의 텍스트 간의 변환 사각형 및 해당 창의 사각형을 표시합니다.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *lprc*  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 도구 팁 창 사각형 또는 텍스트 표시 사각형 중 하나를 보유 하는 구조입니다.  
  
 *bLarger*  
 True 인 경우, *lprc* 텍스트 표시 사각형을 지정 하는 데 사용 하 고 해당 창 사각형을 받습니다. False 인 경우, *lprc* 창 사각형을 지정 하는 데 사용 되 고 해당 텍스트 표시 사각형을 받습니다.  
  
### <a name="return-value"></a>반환 값  
 사각형 성공적으로 조정 되는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 창 사각형 또는 지정 된 텍스트 표시 사각형을 표시 하는 데 필요한 도구 팁 창 사각형에서 도구 설명 컨트롤의 텍스트 표시 사각형을 계산 합니다.  
  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="create"></a>  CToolTipCtrl::Create  
 도구 설명 컨트롤을 만들고에 연결 된 `CToolTipCtrl` 개체입니다.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentWnd*  
 일반적으로 도구 설명 컨트롤의 부모 창 지정을 `CDialog`합니다. NULL이 아니어야 합니다.  
  
 *dwStyle*  
 도구 설명 컨트롤의 스타일을 지정합니다. 참조는 **주의** 한 자세 합니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CToolTipCtrl` 개체는 성공적으로 생성 된, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CToolTipCtrl` 두 단계를 수행에서 합니다. 먼저,을 만드는 생성자를 호출는 `CToolTipCtrl` 개체를 호출 `Create` 도구 설명 컨트롤을 만들고에 연결 하는 `CToolTipCtrl` 개체입니다.  
  
 *dwStyle* 매개 변수의 조합이 포함 될 수 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다. 또한 도구 설명 컨트롤에 서로 다른 두 클래스 관련 스타일: TTS_ALWAYSTIP 및 TTS_NOPREFIX 합니다.  
  
|스타일|의미|  
|-----------|-------------|  
|TTS_ALWAYSTIP|도구를 도구 설명 컨트롤의 소유자 창이 활성 또는 비활성 인지에 관계 없이 커서를 가져갈 때 도구 설명에 표시 됨을 지정 합니다. 이 스타일 없이 도구 설명 컨트롤이 나타나지만 도구의 소유자 창이 활성 상태일 때 되 고 비활성 상태일 때가 아니라.|  
|TTS_NOPREFIX|이 스타일에서 앰퍼샌드 (&)는 문자열에서 문자를 제거 합니다. 시스템을 방지 합니다. 도구 설명 컨트롤 TTS_NOPREFIX 스타일이 없는 경우 시스템 앰퍼샌드 문자를 메뉴 항목으로 및 도구 설명 컨트롤에 텍스트와 동일한 문자열을 사용 하도록 응용 프로그램을 자동으로 제거 합니다.|  
  
 도구 설명 컨트롤에 컨트롤을 만들 때의 지정 여부에 관계 없이 WS_POPUP 및 WS_EX_TOOLWINDOW 창 스타일 있습니다.  
  
 확장된 창 스타일을 사용 하 여 도구 설명 컨트롤을 만들려면 호출 [CToolTipCtrl::CreateEx](#createex) 대신 `Create`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
##  <a name="createex"></a>  CToolTipCtrl::CreateEx  
 와 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CToolTipCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentWnd*  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 *dwStyle*  
 도구 설명 컨트롤의 스타일을 지정합니다. 참조는 **주의** 섹션 [만들기](#create) 자세한 정보에 대 한 합니다.  
  
 *dwStyleEx*  
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 `Create` Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_** 합니다.  
  
##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl  
 `CToolTipCtrl` 개체를 생성합니다.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>설명  
 호출 해야 `Create` 후 개체를 생성 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>  CToolTipCtrl::DelTool  
 로 지정 된 도구를 제거 *pWnd* 및 *nIDTool* 에서 도구 설명 컨트롤에서 지 원하는 도구 컬렉션입니다.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *nIDTool*  
 ID는 도구입니다.  
  
##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize  
 도구 설명의 크기를 검색 합니다.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lpToolInfo*  
 도구 설명에 대 한 포인터 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 도구 설명의 크기입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool  
 현재 도구 설명 컨트롤에서 표시 도구 설명 창의 텍스트, 위치, 크기 등의 정보를 검색 합니다.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] *lpToolInfo*|에 대 한 포인터는 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) 구조체 현재 도구 창에 대 한 정보입니다.|  
  
### <a name="return-value"></a>반환 값  
 정보를 성공적으로 검색 되 면 TRUE 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 현재 도구 창에 대 한 정보를 검색합니다.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime  
 팝업, 초기 검색 하 고 reshow 현재 도구 설명 컨트롤에 대해 설정 하는 기간.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *dwDuration*  
 어떤 기간 값을 지정 하는 플래그 검색 됩니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
- 도구 설명 창 시간의 길이 TTDT_AUTOPOP 검색 포인터가 도구의 경계 사각형 내에서 고정 되어 있는 경우에 표시 됩니다.  
  
- TTDT_INITIAL 검색 포인터 도구 설명 창이 전에 도구의 경계 사각형 내에서 고정 되어 있어야 하는 시간의 길이 나타납니다.  
  
- TTDT_RESHOW 검색 다음 도구 설명 창이 포인터가 표시 하는 데 걸리는 시간의 길이 한 도구에서 다른 위치로 이동 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 지연 시간 (밀리초)  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin  
 위쪽, 왼쪽, 아래쪽 및 오른쪽 여백이 설정에 대 한 도구 설명 창을 검색 합니다.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lprc*  
 주소는 `RECT` 여백 정보를 받을 구조입니다. 멤버는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조는 경계 사각형을 정의 하지 않습니다. 이 메시지를 목적으로 구조체 멤버는 다음과 같이 해석 됩니다.  
  
|멤버|표현|  
|------------|--------------------|  
|`top`|위쪽 테두리와 도구 설명 텍스트 (픽셀)에서의 위쪽 간 거리입니다.|  
|`left`|픽셀 단위로 팁 텍스트의 왼쪽된 끝와 왼쪽된 테두리 사이의 거리입니다.|  
|`bottom`|아래쪽 테두리의 픽셀 단위로 팁 텍스트를 아래쪽 사이의 거리입니다.|  
|`right`|오른쪽 테두리와 픽셀 단위로 팁 텍스트의 오른쪽 끝 간 거리입니다.|  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth  
 도구 설명 창이 대 한 최대 너비를 검색합니다.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 설명 창이 대 한 최대 너비입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="gettext"></a>  CToolTipCtrl::GetText  
 도구 설명 컨트롤을 도구에 대 한 유지 관리 하는 텍스트를 검색 합니다.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *str*  
 에 대 한 참조는 `CString` 도구의 텍스트를 받는 개체입니다.  
  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *nIDTool*  
 ID는 도구입니다.  
  
### <a name="remarks"></a>설명  
 *pWnd* 및 *nIDTool* 매개 변수는 도구를 확인 합니다. 해당 도구 이전에 대 한 이전 호출을 통해 도구 설명 컨트롤에 등록 된 경우 `CToolTipCtrl::AddTool`를 참조 하는 개체는 *str* 매개 변수 도구의 텍스트를 지정 합니다.  
  
##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor  
 도구 설명 창의 배경색을 검색합니다.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 배경색을 나타내는 값입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor  
 도구 설명 창이의 텍스트 색을 검색합니다.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 텍스트 색을 나타내는 값입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle  
 현재 도구 설명 컨트롤의 제목을 검색합니다.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] *pttgt*|에 대 한 포인터는 [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) 도구 설명 컨트롤에 대 한 정보가 포함 된 구조체입니다. 이 메서드가 반환 될 때는 *pszTitle* 의 멤버는 [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) 의 제목 텍스트를 가리키는 구조체입니다.|  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount  
 등록 된 도구 설명 컨트롤이 도구 수를 검색 합니다.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 수가 도구 설명 컨트롤에 등록 합니다.  
  
##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo  
 도구 설명 컨트롤 유지 관리 하는 도구에 대 한 정보를 검색 합니다.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *ToolInfo*  
 에 대 한 참조는 `TOOLINFO` 도구의 텍스트를 받는 개체입니다.  
  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *nIDTool*  
 ID는 도구입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `hwnd` 및 `uId` 의 멤버는 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) 에서 참조 하는 구조 *CToolInfo* 도구를 식별 합니다. 도구 설명 컨트롤에 대 한 이전 호출을 통해 해당 도구에 등록 된 경우 `AddTool`, `TOOLINFO` 구조는 도구에 대 한 정보로 채워집니다.  
  
##  <a name="hittest"></a>  CToolTipCtrl::HitTest  
 지정 된 도구의 경계 사각형 내의 인지 확인 하 고이 경우이 도구에 대 한 정보를 검색 하는 지점을 테스트 합니다.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *pt*  
 에 대 한 포인터는 `CPoint` 테스트할 점의 좌표를 포함 하는 개체입니다.  
  
 *lpToolInfo*  
 에 대 한 포인터 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) 도구에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 적중 테스트 정보에 의해 지정 된 지점 도구의 경계 사각형; 내에 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 0이 아닌 값을 반환 하는 경우 구조 가리키는 *lpToolInfo* 점이 해당 사각형 내에서 도구에 대 한 정보로 채워집니다.  
  
 `TTHITTESTINFO` 구조는 다음과 같이 정의 됩니다.  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 `hwnd`  
 도구의 핸들을 지정합니다.  
  
 `pt`  
 지점이 도구의 경계 사각형 경우 한 점의 좌표를 지정 합니다.  
  
 `ti`  
 이 도구에 대 한 정보입니다. 에 대 한 자세한 내용은 `TOOLINFO` 구조, 참조 [CToolTipCtrl::GetToolInfo](#gettoolinfo)합니다.  
  
##  <a name="pop"></a>  CToolTipCtrl::Pop  
 보기에서 표시 된 도구 설명 창을 제거 합니다.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="popup"></a>  CToolTipCtrl::Popup  
 마지막 마우스 메시지가 좌표에 표시 하려면 현재 도구 설명 컨트롤을 하면 됩니다.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 도구 설명 창이 표시 됩니다.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent  
 처리에 대 한 도구 설명 컨트롤에 마우스 메시지가 전달합니다.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpMsg*  
 에 대 한 포인터는 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) 릴레이로 메시지를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 도구 설명 컨트롤에서 보내는 다음 메시지만 처리 `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|WM_LBUTTONUP|WM_RBUTTONDOWN|  
|WM_MBUTTONDOWN|WM_RBUTTONUP|  
|WM_MBUTTONUP||  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime  
 도구 설명 컨트롤에 대 한 지연 시간을 설정합니다.  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>매개 변수  
 *nDelay*  
 새 지연 시간을 밀리초 단위로 지정 합니다.  
  
 *dwDuration*  
 어떤 기간 값을 지정 하는 플래그 검색 됩니다. 참조 [CToolTipCtrl::GetDelayTime](#getdelaytime) 에 대 한 설명은 유효한 값입니다.  
  
 *iTime*  
 지정 된 지연 시간 (밀리초)에서입니다.  
  
### <a name="remarks"></a>설명  
 지연 시간은 도구 설명 창이 표시 될 때까지 커서 도구 켜져 있어야 하는 시간의 길이입니다. 기본 지연 시간은 500 밀리초입니다.  
  
##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin  
 위쪽, 왼쪽, 아래쪽 및 오른쪽 여백이 도구 설명 창이 대 한 설정합니다.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>매개 변수  
 *lprc*  
 주소는 `RECT` 설정할 여백 정보가 포함 된 구조체입니다. 멤버는 `RECT` 구조는 경계 사각형을 정의 하지 않습니다. 참조 [CToolTipCtrl::GetMargin](#getmargin) 에 대 한 설명은 여백 정보입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth  
 도구 설명 창이 대 한 최대 너비를 설정합니다.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 *iWidth*  
 설정할 최대 도구 팁 창 너비입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 최대 설명 너비입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor  
 도구 설명 창이에서 명령 프롬프트 창의 배경색을 설정합니다.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>매개 변수  
 *clr*  
 새 배경색입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor  
 도구 설명 창이의 텍스트 색을 설정합니다.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>매개 변수  
 *clr*  
 새 텍스트 색입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="settitle"></a>  CToolTipCtrl::SetTitle  
 도구 설명에 아이콘 및 제목을 표준 문자열을 추가합니다.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 *uIcon*  
 참조 *아이콘* 에 [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) Windows sdk에서입니다.  
  
 *lpstrTitle*  
 제목 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo  
 도구 설명 하는 도구에 대 한 유지 관리 하는 정보를 설정 합니다.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpToolInfo*  
 에 대 한 포인터는 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) 설정에 대 한 정보를 지정 하는 구조입니다.  
  
##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect  
 도구에 대 한 새로운 경계 사각형을 설정합니다.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *nIDTool*  
 ID는 도구입니다.  
  
 *lpRect*  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 새 경계 사각형을 지정 하는 구조입니다.  
  
##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme  
 도구 설명 창이의 비주얼 스타일을 설정합니다.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>매개 변수  
 *pszSubAppName*  
 설정 하는 비주얼 스타일을 포함 하는 유니코드 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) Windows SDK에 설명 된 대로 메시지입니다.  
  
##  <a name="update"></a>  CToolTipCtrl::Update  
 현재 도구 다시 그릴를 강제로 수행 합니다.  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText  
 이 컨트롤의이 도구에 대 한 도구 설명 텍스트를 업데이트합니다.  
  
```  
void UpdateTipText(
    LPCTSTR lpszText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);

 
void UpdateTipText(
    UINT nIDText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszText*  
 이 도구에 대 한 텍스트에 대 한 포인터입니다.  
  
 *pWnd*  
 이 도구를 포함 하는 창에 대 한 포인터입니다.  
  
 *nIDTool*  
 ID는 도구입니다.  
  
 *nIDText*  
 이 도구에 대 한 텍스트를 포함 하는 문자열 리소스의 ID입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBar 클래스](../../mfc/reference/ctoolbar-class.md)
