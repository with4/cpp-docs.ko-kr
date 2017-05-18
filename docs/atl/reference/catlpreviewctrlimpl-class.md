---
title: "CAtlPreviewCtrlImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: 26
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 979dc23eabc2ba2362f7301fc34ca89016d58f37
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl 클래스
이 클래스는 풍부한 미리 보기에 대 한 셸에서 제공 하는 호스 창에 배치 된 창의 ATL 구현 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|미리 보기 컨트롤 개체를 destructs 합니다.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|미리 보기 컨트롤 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Windows 창을 만들기 위해 고급 미리 보기 처리기가 호출 됩니다.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|이 컨트롤을 파괴 하는 경우에 풍부한 미리 보기 처리기에 의해 호출 됩니다.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|입력이 컨트롤에 포커스를 설정 합니다.|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|WM_PAINT 메시지를 처리합니다.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|이 컨트롤 다시 그리기를 알려 줍니다.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|이 컨트롤에 대 한 새 부모를 설정합니다.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|호출 하는 풍부한 미리 보기 처리기 풍부한 미리 보기의 시각 효과 설정 하는 경우 콘텐츠.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|이 컨트롤에 대 한 새로운 경계 사각형을 설정합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|미리 보기를 렌더링 하는 프레임 워크에서 호출 됩니다.|  
  
### <a name="protected-constants"></a>보호 된 상수  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|미리 보기 창에 텍스트를 표시 하는 데 사용 하는 글꼴입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|미리 보기 창의 배경색입니다.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|미리 보기 창의 텍스트 색입니다.|  

  
## <a name="remarks"></a>주의  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlpreviewctrlimpl.h  
  
##  <a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 미리 보기 컨트롤 개체를 만듭니다.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="dtor"></a>CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 미리 보기 컨트롤 개체를 destructs 합니다.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="create"></a>CAtlPreviewCtrlImpl::Create  
 Windows 창을 만들기 위해 고급 미리 보기 처리기가 호출 됩니다.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 고급 미리 보기에 대 한 셸 제공한 호스트 창에 대 한 핸들입니다.  
  
 `prc`  
 초기 크기와 창의 위치를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy  
 이 컨트롤을 파괴 하는 경우에 풍부한 미리 보기 처리기에 의해 호출 됩니다.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint  
 미리 보기를 렌더링 하는 프레임 워크에서 호출 됩니다.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>매개 변수  
 `hdc`  
 그리기에 대 한 장치 컨텍스트 핸들입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="focus"></a>CAtlPreviewCtrlImpl::Focus  
 입력이 컨트롤에 포커스를 설정 합니다.  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack  
 미리 보기 창의 배경색입니다.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText  
 미리 보기 창의 텍스트 색입니다.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf  
 미리 보기 창에 텍스트를 표시 하는 데 사용 하는 글꼴입니다.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint  
 WM_PAINT 메시지를 처리합니다.  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMsg`  
 WM_PAINT로 설정 합니다.  
  
 `wParam`  
 이 매개 변수는 사용되지 않습니다.  
  
 `lParam`  
 이 매개 변수는 사용되지 않습니다.  
  
 `bHandled`  
 포함 된이 함수를 반환 하는 경우 `TRUE`합니다.  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw  
 이 컨트롤 다시 그리기를 알려 줍니다.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost  
 이 컨트롤에 대 한 새 부모를 설정합니다.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 새 부모 창에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals  
 호출 하는 풍부한 미리 보기 처리기 풍부한 미리 보기의 시각 효과 설정 하는 경우 콘텐츠.  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>매개 변수  
 `clrBack`  
 미리 보기 창의 배경색입니다.  
  
 `clrText`  
 미리 보기 창의 텍스트 색입니다.  
  
 `plf`  
 미리 보기 창에 텍스트를 표시 하는 데 사용 하는 글꼴입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect  
 이 컨트롤에 대 한 새로운 경계 사각형을 설정합니다.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>매개 변수  
 `prc`  
 새 크기와 미리 보기 컨트롤의 위치를 지정합니다.  
  
 `bRedraw`  
 컨트롤을 다시 그리면 해야 하는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)

