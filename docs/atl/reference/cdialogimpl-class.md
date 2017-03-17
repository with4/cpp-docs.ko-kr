---
title: "CDialogImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: 25
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 732227ef8566ce5e2985a3e65a1153a130df6b20
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogimpl-class"></a>CDialogImpl 클래스
이 클래스는 모달 또는 모덜리스 대화 상자를 만드는 메서드를 제공 합니다.  
  
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
|[DestroyWindow](#destroywindow)|모덜리스 대화 상자를 삭제합니다.|  
|[DoModal](#domodal)|모달 대화 상자를 만듭니다.|  
|[EndDialog](#enddialog)|모달 대화 상자를 삭제합니다.|  
  
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
  
## <a name="remarks"></a>주의  
 와 `CDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CDialogImpl`적절 한 처리기에 메시지를 직접 기본 메시지 맵을 사용 하 여 대화 상자 절차를 제공 합니다.  
  
 기본 클래스 소멸자 **~ CWindowImplRoot** 창은 개체를 삭제 하기 전에 제거 된 것을 확인 합니다.  
  
 `CDialogImpl`파생 되며 **CDialogImplBaseT**, 다시에서 파생 된 **CWindowImplRoot**합니다.  
  
> [!NOTE]
>  클래스를 정의 해야는 **IDD** 대화 상자 템플릿 리소스 ID를 지정 하는 멤버 예를 들어, ATL 프로젝트 마법사는 자동으로 클래스에 다음 줄을 추가합니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&41;](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 여기서 `MyDlg` 는 **약식 이름** 는 마법사에 입력 한 **이름** 페이지입니다.  
  
|추가 정보|참조|  
|--------------------------------|---------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|ATL의 대화 상자를 사용 하 여|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
|대화 상자|[대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms632588) 및 후속 항목에는[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
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
 [in] 소유자 창에 대 한 핸들입니다.  
  
 **RECT / /**`rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 대화 상자의 크기와 위치를 지정 하는 구조입니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 **lParam** 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 대화 상자에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 대화 상자에 자동으로 연결 되는 `CDialogImpl` 개체입니다. 모달 대화 상자를 만들려면 호출 [DoModal](#domodal)합니다. 위의 두 번째 재정의에 사용 됩니다 [CComControl](../../atl/reference/ccomcontrol-class.md)합니다.  
  
##  <a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 모덜리스 대화 상자를 삭제합니다.  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 대화 상자가 성공적으로 소멸 되 고, 그렇지 않으면 되었으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 반환 **TRUE** 대화 상자가 성공적으로 소멸 되 고, 그렇지 않으면 되었으면 **FALSE**합니다.  
  
##  <a name="dialogproc"></a>CDialogImpl::DialogProc  
 이 정적 함수에는 대화 상자 프로시저가 구현합니다.  
  
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
 [in] 대화 상자에 전송 되는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 메시지를 처리 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 `DialogProc`기본 메시지 맵을 사용 하 여 적절 한 처리기에 메시지를 보내도록 합니다.  
  
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
 [in] 소유자 창에 대 한 핸들입니다. 기본값은의 반환 값은 [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 함수입니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 **lParam** 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우의 값은 `nRetCode` 에 대 한 호출에 지정 된 매개 변수가 [EndDialog](#enddialog)합니다. 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 이 대화 상자에 자동으로 연결 되는 `CDialogImpl` 개체입니다.  
  
 모덜리스 대화 상자를 만들려면 호출 [만들기](#create)합니다.  
  
##  <a name="enddialog"></a>CDialogImpl::EndDialog  
 모달 대화 상자를 삭제합니다.  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>매개 변수  
 `nRetCode`  
 [in] 반환 될 값 [CDialogImpl::DoModal](#domodal)합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 대화 상자가 소멸 되 고, 그렇지 않으면 있으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 `EndDialog`대화 상자 프로시저를 통해 호출 되어야 합니다. Windows 값을 사용 하 여 대화 상자 소멸 된 후 `nRetCode` 에 대 한 반환 값으로 `DoModal`, 대화 상자를 만든 합니다.  
  
> [!NOTE]
>  호출 하지 마십시오 `EndDialog` 를 모덜리스 대화 상자를 제거 합니다. 호출 [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) 대신 합니다.  
  
##  <a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 반환 `DialogProc`, 현재 대화 상자 프로시저가 있습니다.  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>반환 값  
 현재 대화 상자 프로시저가 있습니다.  
  
### <a name="remarks"></a>주의  
 고유한 대화 프로시저 대체 하려면이 메서드를 재정의 합니다.  
  
##  <a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 화면에 지정된 된 사각형의 대화 상자 단위 (maps) 단위 (픽셀)를 변환합니다.  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `CRect` 개체 또는 [RECT](../../mfc/reference/rect-structure1.md) 업데이트 영역을 포함 하는 업데이트의 클라이언트 좌표를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 성공 하면 0이 아닌 업데이트가 실패 한 경우 0입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 좌표를 대체 하는 함수 `RECT` 구조 만들기 대화 상자 또는 대화 상자 내에서 컨트롤을 배치 하는 데 사용할 수 있는 변환 된 좌표 구조체입니다.  
  
##  <a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 마지막 메시지를 받은 후에 호출 (일반적으로 `WM_NCDESTROY`).  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 소멸 되 고 창에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 창 소멸 시 개체를 자동으로 삭제 하려는 경우 수 호출할 수는 `delete this;` 여기 있습니다.  
  
##  <a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 대화 상자에 전송 된 메시지를 처리 하는 첫 번째 메시지를 받을 때 한 번만 호출 합니다.  
  
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
 [in] 대화 상자에 전송 되는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 창 프로시저입니다.  
  
### <a name="remarks"></a>주의  
 초기 호출 후 `StartDialogProc`, `DialogProc` 대화 절차 및 추가 호출 이동으로 설정 되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [클래스 개요](../../atl/atl-class-overview.md)
