---
title: CAxDialogImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
dev_langs:
- C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3e1b7d4f88428060f4aa4d01180bce1e970b650
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365079"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl 클래스
이 클래스는 ActiveX 컨트롤을 호스팅하는 (모달 및 모덜리스) 대화 상자를 구현합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `CAxDialogImpl`합니다.  
  
 *TBase*  
 에 대 한 기본 창 클래스 **CDialogImplBaseT**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Advise 하거나 unadvise 개체의 싱크 맵 이벤트 맵에서 모든 항목에이 메서드를 호출 합니다.|  
|[CAxDialogImpl::Create](#create)|모덜리스 대화 상자를 만들려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|모덜리스 대화 상자를 삭제 하려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::DoModal](#domodal)|모달 대화 상자를 만들려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::EndDialog](#enddialog)|모달 대화 상자를 삭제 하려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|이 메서드를 호출에 대 한 포인터를 가져오는 `DialogProc` 콜백 함수입니다.|  
|[CAxDialogImpl::GetIDD](#getidd)|대화 상자 템플릿 리소스 ID를 가져오려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|이 대화 상자는 메시지는 보내집니다 있는지 여부를 확인 하려면이 메서드를 호출 하 고 그럴 경우 메시지를 처리 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|디버그에만 존재 하는 변수 빌드되고 모달 대화 상자를 true로 설정 됩니다.|  
  
## <a name="remarks"></a>설명  
 `CAxDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CAxDialogImpl` 기본 메시지 맵을 메시지를 적절 한 처리기를 사용 하 여 대화 상자 프로시저를 제공 합니다.  
  
 `CAxDialogImpl` 파생 `CDialogImplBaseT`에서 파생 됩니다는 *TBase* (기본적으로 `CWindow`) 및 `CMessageMap`합니다.  
  
 클래스 대화 상자 템플릿 리소스 id입니다. 지정 하는 IDD 멤버를 정의 해야 합니다. 예를 들어, 사용 하 여 ATL 대화 상자 개체를 추가 **클래스 추가** 대화 상자 클래스에 다음 줄을 자동으로 추가 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 여기서 `MyDialog` 는 **약식 이름** ATL 대화 상자 마법사에 입력 합니다.  
  
 참조 [대화 상자를 구현](../../atl/implementing-a-dialog-box.md) 자세한 정보에 대 한 합니다.  
  
 모달 대화 상자에서 ActiveX 컨트롤 사용 하 여 만든 참고 `CAxDialogImpl` 액셀러레이터 키를 지원 하지 것입니다. 사용 하 여 만든 대화 상자에서 액셀러레이터 키를 지원 하기 위해 `CAxDialogImpl`모덜리스 대화 상자를 만들고, 사용 하 여 고유한 메시지 루프를 사용 하 여 [CAxDialogImpl::IsDialogMessage](#isdialogmessage) 처리 하는 큐 로부터 메시지를 받은 후는 액셀러레이터 키입니다.  
  
 대 한 자세한 내용은 `CAxDialogImpl`, 참조 [ATL 컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="advisesinkmap"></a>  CAxDialogImpl::AdviseSinkMap  
 Advise 하거나 unadvise 개체의 싱크 맵 이벤트 맵에서 모든 항목에이 메서드를 호출 합니다.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>매개 변수  
 `bAdvise`  
 알림을 받을 수 있습니다; 모든 싱크 항목이 있는 경우 true로 설정 false 이면 모든 싱크 항목은이 권장 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="create"></a>  CAxDialogImpl::Create  
 모덜리스 대화 상자를 만들려면이 메서드를 호출 합니다.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 [in] 소유자 창 핸들입니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 `lParam` 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
 **RECT &AMP;**  
 이 매개 변수는 사용되지 않습니다. 이 매개 변수는에 의해 전달 된 `CComControl`합니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 대화 상자에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 대화 상자에 자동으로 연결 되는 `CAxDialogImpl` 개체입니다. 모달 대화 상자를 만들려면 호출 [DoModal](#domodal)합니다.  
  
 두 번째 재정의 대화 상자와 함께 사용할 수 있도록 제공 됩니다 [CComControl](../../atl/reference/ccomcontrol-class.md)합니다.  
  
##  <a name="destroywindow"></a>  CAxDialogImpl::DestroyWindow  
 모덜리스 대화 상자를 삭제 하려면이 메서드를 호출 합니다.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면는 창이 성공적으로 소멸 됩니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 호출 하지 마십시오 `DestroyWindow` 모달 대화 상자를 제거할 수 있습니다. 호출 [EndDialog](#enddialog) 대신 합니다.  
  
##  <a name="domodal"></a>  CAxDialogImpl::DoModal  
 모달 대화 상자를 만들려면이 메서드를 호출 합니다.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 [in] 소유자 창 핸들입니다. 기본값은의 반환 값은 [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 함수입니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 `lParam` 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 값의 `nRetCode` 호출에 지정 된 매개 변수 [EndDialog](#enddialog), 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>설명  
 이 대화 상자에 자동으로 연결 되는 `CAxDialogImpl` 개체입니다.  
  
 모덜리스 대화 상자를 만들려면 호출 [만들기](#create)합니다.  
  
##  <a name="enddialog"></a>  CAxDialogImpl::EndDialog  
 모달 대화 상자를 삭제 하려면이 메서드를 호출 합니다.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nRetCode`  
 [in] 반환 될 값 [DoModal](#domodal)합니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 대화 상자가 소멸 됩니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 `EndDialog` 대화 상자 프로시저를 통해 호출 되어야 합니다. Windows 대화 상자 소멸 되기 후의 값을 사용 `nRetCode` 에 대 한 반환 값으로 `DoModal`, 대화 상자를 생성 합니다.  
  
> [!NOTE]
>  호출 하지 마십시오 `EndDialog` 모덜리스 대화 상자를 제거할 수 있습니다. 호출 [DestroyWindow](#destroywindow) 대신 합니다.  
  
##  <a name="getdialogproc"></a>  CAxDialogImpl::GetDialogProc  
 이 메서드를 호출에 대 한 포인터를 가져오는 `DialogProc` 콜백 함수입니다.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 `DialogProc` 콜백 함수입니다.  
  
### <a name="remarks"></a>설명  
 `DialogProc` 함수는 응용 프로그램에서 정의 된 콜백 함수입니다.  
  
##  <a name="getidd"></a>  CAxDialogImpl::GetIDD  
 대화 상자 템플릿 리소스 ID를 가져옵니다.이 메서드를 호출 합니다.  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자 템플릿 리소스 ID를 반환 합니다.  
  
##  <a name="isdialogmessage"></a>  CAxDialogImpl::IsDialogMessage  
 이 대화 상자는 메시지는 보내집니다 있는지 여부를 확인 하려면이 메서드를 호출 하 고 그럴 경우 메시지를 처리 합니다.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMsg`  
 에 대 한 포인터는 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) 검사할 메시지를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지 되었음을 처리 되 고, FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 메시지 루프 내에서 호출 하는 데 사용 됩니다.  
  
##  <a name="m_bmodal"></a>  CAxDialogImpl::m_bModal  
 디버그에만 존재 하는 변수 빌드되고 모달 대화 상자를 true로 설정 됩니다.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>참고 항목  
 [CDialogImpl 클래스](../../atl/reference/cdialogimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
