---
title: IViewObjectExImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3eb40b5b886407a87e0633052cde67868d756a88
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883647"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl 클래스
이 클래스는 구현 `IUnknown` 의 기본 구현을 제공 하 고는 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)를 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), 및 [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `IViewObjectExImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|장치 컨텍스트에 컨트롤의 표시를 그립니다.|  
|[IViewObjectExImpl::Freeze](#freeze)|까지 변경 되지 않습니다 있도록 그려지는 표현을 컨트롤의 고정을 `Unfreeze`입니다. ATL 구현 E_NOTIMPL을 반환합니다.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|있는 경우 컨트롤의 기존 자문 싱크 연결을 검색 합니다.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|그리는 데 컨트롤에서 논리 팔레트를 반환 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|  
|[IViewObjectExImpl::GetExtent](#getextent)|컨트롤 클래스 데이터 멤버에서 컨트롤의 디스플레이 크기 HIMETRIC 단위 (단위당 0.01mm)) 검색 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)합니다.|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|사용자가 사용 하 고 개체의 컨테이너에서 크기 조정 힌트를 제공 합니다.|  
|[IViewObjectExImpl::GetRect](#getrect)|요청한 그리기 모양을 설명 하는 사각형을 반환 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|개체 및 그리기 모양 지의 불투명도 대 한 정보를 반환 합니다.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|지정된 된 지점이 지정된 된 사각형에 있고 반환 경우 확인을 [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) 값 `pHitResult`합니다.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|컨트롤의 표시 사각형 겹치는 사각형을 지정 된 위치에서 든 지 여부를 확인 하 HITRESULT 값을 반환 합니다 `pHitResult`합니다.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|싱크 컨트롤의 보기에서 변경 내용에 대 한 알림을 받을 수 있도록 컨트롤과 advise 싱크 간의 연결을 설정 합니다.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|컨트롤의 그려지는 표시를 해제 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)를 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), 및 [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) 인터페이스를 직접 표시 하 고을 알리기 위해 advise 싱크를 만들고 컨트롤을 사용 하도록 설정 합니다 컨테이너 컨트롤 디스플레이의 변경 내용입니다. `IViewObjectEx` 인터페이스 깜박임 그리기, 사각형이 아닌 투명 한 컨트롤 및 적중 테스트 (예를 들어, 얼마나 근접 마우스 클릭 해야 컨트롤에 간주 되기 위해)와 같은 확장 된 컨트롤 기능에 대 한 지원을 제공 합니다. 클래스 `IViewObjectExImpl` 이러한 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="draw"></a>  IViewObjectExImpl::Draw  
 장치 컨텍스트에 컨트롤의 표시를 그립니다.  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 `CComControl::OnDrawAdvanced` 차례로 호출 하는 컨트롤 클래스의 `OnDraw` 메서드. `OnDraw` 메서드가 ATL 컨트롤 마법사를 사용 하 여 컨트롤을 만들 때 자동으로 컨트롤 클래스에 추가 됩니다. 마법사의 기본 `OnDraw` "ATL 3.0" 레이블이 있는 사각형을 그립니다.  
  
 참조 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) Windows SDK에에서 있습니다.  
  
##  <a name="freeze"></a>  IViewObjectExImpl::Freeze  
 까지 변경 되지 않습니다 있도록 그려지는 표현을 컨트롤의 고정을 `Unfreeze`입니다. ATL 구현 E_NOTIMPL을 반환합니다.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>설명  
 참조 [IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) Windows SDK에에서 있습니다.  
  
##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise  
 있는 경우 컨트롤의 기존 자문 싱크 연결을 검색 합니다.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>설명  
 자문 싱크 컨트롤 클래스 데이터 멤버에 저장 됩니다 [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)합니다.  
  
 참조 [IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) Windows SDK에에서 있습니다.  
  
##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet  
 그리는 데 컨트롤에서 논리 팔레트를 반환 합니다. ATL 구현 E_NOTIMPL을 반환합니다.  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>설명  
 참조 [IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) Windows SDK에에서 있습니다.  
  
##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent  
 컨트롤 클래스 데이터 멤버에서 컨트롤의 디스플레이 크기 HIMETRIC 단위 (단위당 0.01mm)) 검색 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)합니다.  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>설명  
 참조 [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Windows SDK에에서 있습니다.  
  
##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent  
 사용자가 사용 하 고 개체의 컨테이너에서 크기 조정 힌트를 제공 합니다.  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>설명  
 하는 경우 `dwAspect` DVASPECT_CONTENT 됩니다 및 *pExtentInfo dwExtentMode->* DVEXTENT_CONTENT를 설정 하는 * `psizel` control 클래스의 데이터 멤버에 [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)합니다. 이 고, 그렇지 오류 HRESULT를 반환합니다.  
  
 참조 [IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) Windows SDK에에서 있습니다.  
  
##  <a name="getrect"></a>  IViewObjectExImpl::GetRect  
 요청한 그리기 모양을 설명 하는 사각형을 반환 합니다. ATL 구현 E_NOTIMPL을 반환합니다.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>설명  
 참조 [IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) Windows SDK에에서 있습니다.  
  
##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus  
 개체 및 그리기 모양 지의 불투명도 대 한 정보를 반환 합니다.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>설명  
 기본적으로 ATL 설정 `pdwStatus` 컨트롤 VIEWSTATUS_OPAQUE 지원함을 나타내기 위해 (가능한 값은는 [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) 열거형)입니다.  
  
 참조 [IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) Windows SDK에에서 있습니다.  
  
##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint  
 지정된 된 지점이 지정된 된 사각형에 있고 반환 경우 확인을 [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) 값 `pHitResult`합니다.  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>설명  
 HITRESULT_HIT 또는 HITRESULT_OUTSIDE 값일 수 있습니다.  
  
 하는 경우 `dwAspect` equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), 메서드가 S_OK를 반환 합니다. 그렇지 않으면 메서드는 E_FAIL을 반환합니다.  
  
 참조 [IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) Windows SDK에에서 있습니다.  
  
##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect  
 컨트롤의 표시 사각형 겹치는 사각형을 지정 된 위치에서 든 지 반환 여부를 확인 한 [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) 값 `pHitResult`합니다.  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>설명  
 HITRESULT_HIT 또는 HITRESULT_OUTSIDE 값일 수 있습니다.  
  
 하는 경우 `dwAspect` equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), 메서드가 S_OK를 반환 합니다. 그렇지 않으면 메서드는 E_FAIL을 반환합니다.  
  
 참조 [IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) Windows SDK에에서 있습니다.  
  
##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise  
 싱크 컨트롤의 보기에서 변경 내용에 대 한 알림을 받을 수 있도록 컨트롤과 advise 싱크 간의 연결을 설정 합니다.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>설명  

 에 대 한 포인터를 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) advise 싱크 인터페이스 컨트롤 클래스 데이터 멤버에 저장 됩니다 [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink)합니다.  

  
 참조 [IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) Windows SDK에에서 있습니다.  
  
##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze  
 컨트롤의 그려지는 표시를 해제 합니다. ATL 구현 E_NOTIMPL을 반환합니다.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>설명  
 참조 [IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) Windows SDK에에서 있습니다.  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 이 개체와 연결 된 핸들을 종료 하려면이 메서드를 구현 합니다.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>매개 변수  
 *hHandle*  
 핸들을 닫아야입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패 시 오류 HRESULT에서 S_OK를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여이 개체를 사용 하 여 이전에 연결 된이 메서드에 전달 된 핸들이 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
### <a name="example"></a>예  
 다음 코드의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::CloseHandle`합니다.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 이 개체를 사용 하 여 연결 핸들에 신호 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwParam*  
 사용자 매개 변수입니다.  
  
 *hObject*  
 신호에 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패 시 오류 HRESULT에서 S_OK를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여이 개체를 사용 하 여 이전에 연관 된 핸들과이 메서드에 전달 되는 DWORD/포인터 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
### <a name="example"></a>예  
 다음 코드의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::Execute`합니다.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX 컨트롤 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [자습서](../../atl/active-template-library-atl-tutorial.md)   
 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
