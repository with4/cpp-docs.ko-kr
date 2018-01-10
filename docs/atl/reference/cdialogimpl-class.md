---
title: "CDialogImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
dev_langs: C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab4bb1e04bd21900cdf8d8122af51547e79aea22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdialogimpl-class"></a>CDialogImpl 클래스
이 클래스는 모달 또는 모덜리스 대화 상자를 생성 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `CDialogImpl`합니다.  
  
 *TBase*  
 새 클래스의 기본 클래스입니다. 기본 클래스는 [CWindow](../../atl/reference/cwindow-class.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[만들기](#create)|모덜리스 대화 상자를 만듭니다.|  
|[DestroyWindow](#destroywindow)|모덜리스 대화 상자를 제거합니다.|  
|[DoModal](#domodal)|모달 대화 상자를 만듭니다.|  
|[EndDialog](#enddialog)|모달 대화 상자를 제거합니다.|  
  
### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT 메서드  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|현재 대화 상자 프로시저를 반환합니다.|  
|[MapDialogRect](#mapdialogrect)|화면 단위 (픽셀)를 지정된 된 사각형의 대화 상자 단위를 매핑합니다.|  
|[OnFinalMessage](#onfinalmessage)|일반적으로 마지막 메시지를 받은 후에 호출 `WM_NCDESTROY`합니다.|  
  
### <a name="static-functions"></a>정적 함수  
  
|||  
|-|-|  
|[DialogProc](#dialogproc)|대화 상자에 전송 된 메시지를 처리 합니다.|  
|[StartDialogProc](#startdialogproc)|대화 상자에 전송 된 메시지를 처리 하는 첫 번째 메시지를 받을 때 호출 됩니다.|  
  
## <a name="remarks"></a>설명  
 와 `CDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CDialogImpl`기본 메시지 맵을 메시지를 적절 한 처리기를 사용 하 여 대화 상자 프로시저를 제공 합니다.  
  
 기본 클래스 소멸자 **~ CWindowImplRoot** 하면 창 개체를 제거 하기 전에 완료 됩니다.  
  
 `CDialogImpl`파생 **CDialogImplBaseT**에서 파생 됩니다는 **CWindowImplRoot**합니다.  
  
> [!NOTE]
>  클래스를 정의 해야는 **IDD** 대화 상자 템플릿 리소스 id입니다. 지정 하는 멤버 예를 들어, ATL 프로젝트 마법사는 자동으로 클래스에 다음 줄을 추가합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 여기서 `MyDlg` 는 **약식 이름** 는 마법사에서 입력 한 **이름** 페이지.  
  
|추가 정보|보기|  
|--------------------------------|---------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|Atl에서 대화 상자를 사용 하 여|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
|대화 상자|[대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms632588) 및 Windows SDK의 후속 항목|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="create"></a>CDialogImpl::Create  
 모덜리스 대화 상자를 만듭니다.  
  
```  
HWND Create(
    HWND hWndParent,  
    LPARAM dwInitParam = NULL );  

HWND Create(
    HWND hWndParent,  
    RECT&, 
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 [in] 소유자 창 핸들입니다.  
  
 **RECT &**`rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 대화 상자의 크기와 위치를 지정 하는 구조입니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 **lParam** 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 대화 상자에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 대화 상자에 자동으로 연결 되는 `CDialogImpl` 개체입니다. 모달 대화 상자를 만들려면 호출 [DoModal](#domodal)합니다. 위의 두 번째 재정의에 사용 됩니다 [CComControl](../../atl/reference/ccomcontrol-class.md)합니다.  
  
##  <a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 모덜리스 대화 상자를 제거합니다.  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 대화 상자 했으면 성공적으로 제거 된 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 반환 **TRUE** 대화 상자 했으면 성공적으로 제거 된 **FALSE**합니다.  
  
##  <a name="dialogproc"></a>CDialogImpl::DialogProc  
 이 정적 함수는 대화 상자 프로시저를 구현합니다.  
  
```  
 
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);

 
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 대화 상자에 대 한 핸들입니다.  
  
 `uMsg`  
 [in] 대화 상자에 전달 하는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 처리 되 고, 그렇지 않으면 메시지가 있으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 `DialogProc`기본 메시지 맵을 사용 하 여 메시지를 적절 한 처리기.  
  
 재정의할 수 `DialogProc` 메시지를 처리 하기 위한 다른 메커니즘을 제공 합니다.  
  
##  <a name="domodal"></a>CDialogImpl::DoModal  
 모달 대화 상자를 만듭니다.  
  
```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 [in] 소유자 창 핸들입니다. 기본값은의 반환 값은 [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 함수입니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 **lParam** 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 값은 `nRetCode` 호출에 지정 된 매개 변수 [EndDialog](#enddialog)합니다. 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>설명  
 이 대화 상자에 자동으로 연결 되는 `CDialogImpl` 개체입니다.  
  
 모덜리스 대화 상자를 만들려면 호출 [만들기](#create)합니다.  
  
##  <a name="enddialog"></a>CDialogImpl::EndDialog  
 모달 대화 상자를 제거합니다.  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>매개 변수  
 `nRetCode`  
 [in] 반환 될 값 [CDialogImpl::DoModal](#domodal)합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 대화 상자가 고, 그렇지 않으면 제거 된 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 `EndDialog`대화 상자 프로시저를 통해 호출 되어야 합니다. Windows 대화 상자 소멸 되기 후의 값을 사용 `nRetCode` 에 대 한 반환 값으로 `DoModal`, 대화 상자를 생성 합니다.  
  
> [!NOTE]
>  호출 하지 마십시오 `EndDialog` 모덜리스 대화 상자를 제거할 수 있습니다. 호출 [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) 대신 합니다.  
  
##  <a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 반환 `DialogProc`, 현재 대화 상자 프로시저입니다.  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>반환 값  
 현재 대화 상자 프로시저입니다.  
  
### <a name="remarks"></a>설명  
 고유한 대화 상자 프로시저 대체 하려면이 메서드를 재정의 합니다.  
  
##  <a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 화면에 지정된 된 사각형의 대화 상자 단위 (maps) 단위 (픽셀)를 변환합니다.  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `CRect` 개체 또는 [RECT](../../mfc/reference/rect-structure1.md) 업데이트 영역을 포함 하는 업데이트의 클라이언트 좌표를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트에 성공 하면 0이 아닌 업데이트가 실패 한 경우 0입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.  
  
### <a name="remarks"></a>설명  
 함수는 지정 된 좌표를 대체 `RECT` 좌표로 변환된 된 구조체 구조 대화 상자를 만들거나 대화 상자 내에서 컨트롤을 배치 하는 데 사용할 수 있습니다.  
  
##  <a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 마지막 메시지를 받은 후에 호출 (일반적으로 `WM_NCDESTROY`).  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 제거 되 고 한 창 핸들입니다.  
  
### <a name="remarks"></a>설명  
 창 소멸 시 개체를 자동으로 삭제 하려는 경우 수 호출할 수는 `delete this;` 여기 합니다.  
  
##  <a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 대화 상자에 보내는 메시지를 처리 첫 번째 메시지를 받을 때 한 번만 호출 합니다.  
  
```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 대화 상자에 대 한 핸들입니다.  
  
 `uMsg`  
 [in] 대화 상자에 전달 하는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 창 프로시저입니다.  
  
### <a name="remarks"></a>설명  
 초기 호출 후 `StartDialogProc`, `DialogProc` 대화 프로시저와 다른 호출 랭 대로 설정 되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [클래스 개요](../../atl/atl-class-overview.md)