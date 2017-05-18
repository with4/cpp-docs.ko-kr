---
title: "CStatusBarCtrl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CStatusBarCtrl
- CStatusBarCtrl class
- status bar controls
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: d9fc341963572e343123994577a1bec735775386
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl 클래스
Windows의 공용 상태 표시줄 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|`CStatusBarCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|상태 표시줄 컨트롤을 만들고에 연결 된 `CStatusBarCtrl` 개체입니다.|  
|[CStatusBarCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 상태 표시줄 컨트롤을 만들고에 연결 된 `CStatusBarCtrl` 개체입니다.|  
|[CStatusBarCtrl::DrawItem](#drawitem)|소유자 그리기 상태 표시줄 컨트롤의 시각적 측면이 때 호출 됩니다.|  
|[CStatusBarCtrl::GetBorders](#getborders)|상태 표시줄 컨트롤의 가로 및 세로 테두리의 현재 너비를 검색합니다.|  
|[CStatusBarCtrl::GetIcon](#geticon)|현재 상태 표시줄 컨트롤의 부분 (창)에 대 한 아이콘을 검색합니다.|  
|[CStatusBarCtrl::GetParts](#getparts)|상태 표시줄 컨트롤의 파트 수를 검색합니다.|  
|[CStatusBarCtrl::GetRect](#getrect)|상태 표시줄 컨트롤에 있는 파트의 경계 사각형을 검색 합니다.|  
|[Cstatusbarctrl:: Gettext](#gettext)|상태 표시줄 컨트롤의 특정된 부분에서 텍스트를 검색합니다.|  
|[Cstatusbarctrl:: Gettextlength](#gettextlength)|상태 표시줄 컨트롤의 특정된 부분에서 텍스트의 문자에서 길이 검색 합니다.|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|상태 표시줄에 창에 대 한 도구 설명 텍스트를 검색합니다.|  
|[CStatusBarCtrl::IsSimple](#issimple)|단순 모드에 있는지 확인 하려면 상태 창 컨트롤을 확인 합니다.|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|상태 표시줄의 배경색을 설정합니다.|  
|[CStatusBarCtrl::SetIcon](#seticon)|상태 표시줄에는 창에 대 한 아이콘을 설정합니다.|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|표시줄 컨트롤의 그리기 영역 상태의 최소 높이 설정합니다.|  
|[CStatusBarCtrl::SetParts](#setparts)|상태 표시줄 컨트롤, 각 파트의 오른쪽 가장자리의 좌표에에서 파트 수를 설정합니다.|  
|[CStatusBarCtrl::SetSimple](#setsimple)|상태 표시줄 컨트롤 간단한 텍스트를 표시 한 이전 호출에 의해 설정 되는 모든 컨트롤 구성 요소를 표시 하는지 여부를 지정 `SetParts`합니다.|  
|[CStatusBarCtrl::SetText](#settext)|상태 표시줄 컨트롤의 특정 부분에서 텍스트를 설정합니다.|  
|[CStatusBarCtrl::SetTipText](#settiptext)|상태 표시줄에는 창에 대 한 도구 설명 텍스트를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 "상태 표시줄 컨트롤"는 가로 창, 일반적으로 응용 프로그램 다양 한 종류의 상태 정보를 표시할 수 있는 부모 창의 맨 아래에 표시 됩니다. 상태 표시줄 컨트롤은 둘 이상의 유형의 정보를 표시 하는 부분으로 나눌 수 있습니다.  
  
 이 컨트롤 (및 따라서는 `CStatusBarCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CStatusBarCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [를 사용 하 여 CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="create"></a>CStatusBarCtrl::Create  
 상태 표시줄 컨트롤을 만들고에 연결 된 `CStatusBarCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 상태 표시줄 컨트롤의 스타일을 지정합니다. 상태 표시줄에 나열 된 컨트롤 스타일의 조합을 적용 [공통 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이 매개 변수를 포함 해야 합니다는 **WS_CHILD** 스타일입니다. 도 포함 됩니다는 **WS_VISIBLE** 스타일입니다.  
  
 `rect`  
 상태 표시줄 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 `pParentWnd`  
 상태 표시줄 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL입니다.**  
  
 `nID`  
 상태 표시줄 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CStatusBarCtrl` 두 단계를 수행에서 합니다. 먼저 생성자를 호출 하 고 호출 **만들기**, 상태 표시줄 컨트롤을 만들고에 연결 하는 `CStatusBarCtrl` 개체입니다.  
  
 상태 창의 기본 위치는 부모 창의 아래쪽을 따라 있지만 지정할 수 있습니다는 `CCS_TOP` 부모 창의 클라이언트 영역 위쪽에서 열지를 스타일입니다. 지정할 수는 **SBARS_SIZEGRIP** 스타일 상태 창의 오른쪽 끝에 크기 조정 그립을 포함 하도록 합니다. 결합 된 `CCS_TOP` 및 **SBARS_SIZEGRIP** 스타일 있으므로 권장 되지 않습니다, 시스템 상태 창에 그리는 경우에 결과 크기 조정 그립 작동 하지 않습니다.  
  
 확장된 창 스타일을 사용 하 여 상태 표시줄을 만들려면 호출 [CStatusBarCtrl::CreateEx](#createex) 대신 **만들기**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>CStatusBarCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CStatusBarCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 상태 표시줄 컨트롤의 스타일을 지정합니다. 상태 표시줄에 나열 된 컨트롤 스타일의 조합을 적용 [공통 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이 매개 변수를 포함 해야 합니다는 **WS_CHILD** 스타일입니다. 도 포함 됩니다는 **WS_VISIBLE** 스타일입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_**합니다.  
  
##  <a name="cstatusbarctrl"></a>CStatusBarCtrl::CStatusBarCtrl  
 `CStatusBarCtrl` 개체를 생성합니다.  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="drawitem"></a>CStatusBarCtrl::DrawItem  
 소유자 그리기 상태 표시줄 컨트롤의 시각적 측면이 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 긴 포인터는 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) 드로잉 필요한의 종류에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>주의  
 **itemAction** 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업을 수행 하는 것입니다.  
  
 기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CStatusBarCtrl` 개체입니다.  
  
 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 `lpDrawItemStruct` 함수 종료 전에이 멤버입니다.  
  
##  <a name="getborders"></a>CStatusBarCtrl::GetBorders  
 상태 표시줄 컨트롤의 현재 너비 가로 및 세로 테두리의 및 사각형 사이의 간격을 검색합니다.  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pBorders*  
 세 개의 요소가 있는 정수 배열의 주소입니다. 첫 번째 요소 가로 테두리의 너비, 두 번째 세로 테두리의 두께 받는 받아 세 번째 사각형 사이의 테두리의 두께 수신 합니다.  
  
 *nHorz*  
 가로 테두리의 두께 수신 하는 정수에 대 한 참조입니다.  
  
 *변환*  
 세로 테두리의 두께 수신 하는 정수에 대 한 참조입니다.  
  
 *nSpacing*  
 사각형 사이의 테두리의 두께 수신 하는 정수에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이러한 테두리는 컨트롤의 바깥쪽 가장자리와 텍스트가 포함 된 컨트롤 내에서 사각형 사이의 간격을 결정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="geticon"></a>CStatusBarCtrl::GetIcon  
 현재 상태 표시줄 컨트롤의 부분 (창)에 대 한 아이콘을 검색합니다.  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iPart`|검색 아이콘을 포함 하는 파트의 0부터 시작 하는 인덱스입니다. 이 매개 변수는-1, 상태 표시줄 단순 모드 상태 표시줄 것으로 간주 됩니다.|  
  
### <a name="return-value"></a>반환 값  
 아이콘에 대 한 핸들 경우 성공 메서드 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744) 에 설명 되어 있는 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 상태 표시줄 컨트롤 파트 라 하 고 텍스트 출력 창 행으로 구성 됩니다. 상태 표시줄에 대 한 자세한 내용은 참조 [MFC의 상태 표시줄 구현](../../mfc/status-bar-implementation-in-mfc.md) 및 [CStatusBarCtrl 개체의 모드 설정](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_statusBar`즉, 현재 상태 표시줄 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1; 1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 상태 표시줄 컨트롤의 두 창에 아이콘을 복사합니다. 코드 예제에서는 이전 단원에서는 세 개의 창이 사용 하 여 상태 표시줄 컨트롤을 만든 하 고 첫 번째 창에 아이콘을 추가 합니다. 이 예에서는 첫 번째 창에서 아이콘을 검색 하 고 두 번째 및 세 번째 창에 추가 합니다.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1; 2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="getparts"></a>CStatusBarCtrl::GetParts  
 상태 표시줄 컨트롤의 파트 수를 검색합니다.  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nParts`  
 좌표를 검색 하려는 파트 수입니다. 이 매개 변수 컨트롤의 파트 수보다 큰 경우 메시지만의 기존 파트에 대 한 좌표를 검색 합니다.  
  
 *pParts*  
 로 지정 된 파트 수와 동일한 요소 수 있는 정수 배열의 주소 `nParts`합니다. 배열의 각 요소는 해당 파트의 오른쪽 가장자리의 클라이언트 좌표를 받습니다. 요소는-으로 설정 된 경우 해당 파트에 대 한 오른쪽 가장자리의 위치 1, 상태 표시줄의 오른쪽 가장자리를 확장 합니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤이 나 컨트롤 성공 하면 0이 고, 그렇지의 파트 수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 또한 부분의 지정 된 수의 오른쪽 가장자리의 좌표를 검색 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="getrect"></a>CStatusBarCtrl::GetRect  
 상태 표시줄 컨트롤에 있는 파트의 경계 사각형을 검색 합니다.  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nPane`  
 해당 경계 사각형을 검색 하려면 부분의 0부터 시작 인덱스입니다.  
  
 `lpRect`  
 주소는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조체는 경계 사각형입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="gettext"></a>Cstatusbarctrl:: Gettext  
 상태 표시줄 컨트롤의 특정된 부분에서 텍스트를 검색합니다.  
  
```  
CString GetText(
    int nPane,  
    int* pType = NULL) const;  
  
int GetText(
    LPCTSTR lpszText,  
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 텍스트를 수신 하는 버퍼의 주소입니다. 이 매개 변수는 null로 끝나는 문자열.  
  
 `nPane`  
 텍스트를 검색할 부분의 0부터 시작 인덱스입니다.  
  
 `pType`  
 형식 정보를 수신 하는 정수에 대 한 포인터입니다. 유형에 다음이 값 중 하나일 수 있습니다.  
  
- **0** 상태 표시줄의 평면 보다 낮은 표시의 테두리와 텍스트를 그리는 합니다.  
  
- `SBT_NOBORDERS`텍스트 테두리가 그려집니다.  
  
- `SBT_POPOUT`상태 표시줄의 평면 보다 상위 표시의 테두리와 텍스트를 그립니다.  
  
- `SBT_OWNERDRAW`텍스트에는 `SBT_OWNERDRAW` 드로잉 형식 `pType` 이 메시지를 수신 하 고 길이 및 작업 형식 대신 텍스트와 관련 된 32 비트 값을 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 텍스트의 문자에서 길이 또는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 현재 텍스트를 포함 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="gettextlength"></a>Cstatusbarctrl:: Gettextlength  
 상태 표시줄 컨트롤의 특정된 부분에서 텍스트의 문자에서 길이 검색합니다.  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nPane`  
 텍스트를 검색할 부분의 0부터 시작 인덱스입니다.  
  
 `pType`  
 형식 정보를 수신 하는 정수에 대 한 포인터입니다. 유형에 다음이 값 중 하나일 수 있습니다.  
  
- **0** 상태 표시줄의 평면 보다 낮은 표시의 테두리와 텍스트를 그리는 합니다.  
  
- `SBT_NOBORDERS`텍스트 테두리가 그려집니다.  
  
- `SBT_OWNERDRAW`부모 창에서 텍스트를 그립니다.  
  
- `SBT_POPOUT`상태 표시줄의 평면 보다 상위 표시의 테두리와 텍스트를 그립니다.  
  
### <a name="return-value"></a>반환 값  
 텍스트의 문자 길이입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="gettiptext"></a>CStatusBarCtrl::GetTipText  
 상태 표시줄에 창에 대 한 도구 설명 텍스트를 검색합니다.  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nPane`  
 상태 표시줄 창 도구 설명 텍스트를 받을 수의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 도구 설명에 사용할 텍스트를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="issimple"></a>CStatusBarCtrl::IsSimple  
 단순 모드에 있는지 확인 하려면 상태 창 컨트롤을 확인 합니다.  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태 창 컨트롤은 단순 모드;에 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor  
 상태 표시줄의 배경색을 설정합니다.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>매개 변수  
 `cr`  
 **COLORREF** 새 배경 색을 지정 하는 값입니다. 지정 된 `CLR_DEFAULT` 값을 해당 기본 배경색을 사용 하려면 상태 표시줄을 발생 합니다.  
  
### <a name="return-value"></a>반환 값  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 이전 기본 배경색을 나타내는 값입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="seticon"></a>CStatusBarCtrl::SetIcon  
 상태 표시줄에는 창에 대 한 아이콘을 설정합니다.  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPane`  
 창 아이콘 받을의 0부터 시작 하는 인덱스입니다. 이 매개 변수는-1, 상태 표시줄 단순 상태 표시줄 것으로 간주 됩니다.  
  
 `hIcon`  
 설정 아이콘에 대 한 핸들입니다. 이 값이 **NULL**, 아이콘이 부분에서 제거 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CStatusBarCtrl::SetBkColor](#setbkcolor)합니다.  
  
##  <a name="setminheight"></a>CStatusBarCtrl::SetMinHeight  
 표시줄 컨트롤의 그리기 영역 상태의 최소 높이 설정합니다.  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMin`  
 컨트롤의 픽셀의 최소 높이입니다.  
  
### <a name="remarks"></a>주의  
 최소 높이의 합은 `nMin` 및 상태 표시줄 컨트롤의 세로 테두리의 픽셀에서 너비 두 배입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="setparts"></a>CStatusBarCtrl::SetParts  
 상태 표시줄 컨트롤, 각 파트의 오른쪽 가장자리의 좌표에에서 파트 수를 설정합니다.  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>매개 변수  
 `nParts`  
 설정 하는 파트 수입니다. 파트 수는 255 보다 클 수 없습니다.  
  
 *pWidths*  
 예: 동일한 요소 수로 지정 된 부분으로 정수 배열의 주소 `nParts`합니다. 배열의 각 요소는 해당 파트의 오른쪽 가장자리의 위치를 클라이언트 좌표를 지정합니다. 요소는-1, 컨트롤의 오른쪽 가장자리에 해당 부분에 대 한 오른쪽 가장자리의 위치를 확장 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="setsimple"></a>CStatusBarCtrl::SetSimple  
 상태 표시줄 컨트롤 간단한 텍스트를 표시 한 이전 호출에 의해 설정 되는 모든 컨트롤 구성 요소를 표시 하는지 여부를 지정 [SetParts](#setparts)합니다.  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSimple`  
 표시 유형을 플래그입니다. 이 매개 변수가 `TRUE`, 컨트롤은이 경우 간단한 텍스트; 표시 `FALSE`, 여러 부분을 표시 합니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램 변경 되 면 상태 표시줄 컨트롤에서 비 단순 simple로 또는 그 반대로 시스템 컨트롤을 즉시 다시 그립니다.  
  
##  <a name="settext"></a>CStatusBarCtrl::SetText  
 상태 표시줄 컨트롤의 특정 부분에서 텍스트를 설정합니다.  
  
```  
BOOL SetText(
    LPCTSTR lpszText,  
    int nPane,  
    int nType);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 설정할 텍스트를 지정하는 null 종료 문자열의 주소입니다. `nType`이 `SBT_OWNERDRAW`인 경우 `lpszText`는 32비트 데이터를 나타냅니다.  
  
 `nPane`  
 설정할 부분의 0부터 시작하는 인덱스입니다. 이 값이 255인 경우에는 상태 표시줄 컨트롤이 하나의 부분만 있는 단일 컨트롤인 것으로 간주됩니다.  
  
 `nType`  
 그리기 작업의 형식입니다. 참조 [SB_SETTEXT 메시지](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx) 목록이 가능한 값에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메시지는 컨트롤에서 변경된 부분을 무효화하고 이 컨트롤이 다음에 `WM_PAINT` 메시지를 수신할 때 새 텍스트가 표시되도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="settiptext"></a>CStatusBarCtrl::SetTipText  
 상태 표시줄에는 창에 대 한 도구 설명 텍스트를 설정합니다.  
  
```  
void SetTipText(
    int nPane,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPane`  
 상태 표시줄 창 도구 설명 텍스트를 받을 수의 0부터 시작 하는 인덱스입니다.  
  
 *pszTipText*  
 도구 설명 텍스트를 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatusBarCtrl # 12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl 클래스](../../mfc/reference/ctoolbarctrl-class.md)

