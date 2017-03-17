---
title: "CStockPropImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
dev_langs:
- C++
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 366da264f62364a39f6dfe9903a1a19a89266d33
ms.lasthandoff: 02/24/2017

---
# <a name="cstockpropimpl-class"></a>CStockPropImpl 클래스
이 클래스는 주식 속성 값을 지원 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE CStockPropImpl : public IDispatchImpl<InterfaceName, piid,
 plibid,
    wMajor,
 wMinor,
    tihclass>
```   
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 되 고 컨트롤을 구현 하는 클래스 `CStockPropImpl`합니다.  
  
 `InterfaceName`  
 스톡 속성을 노출 하는 이중 인터페이스입니다.  
  
 `piid`  
 에 대 한 포인터의 IID `InterfaceName`합니다.  
  
 `plibid`  
 정의 포함 하는 형식 라이브러리의 LIBID에 대 한 포인터 `InterfaceName`합니다.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다. 기본값은 1입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다. 기본값은 0입니다.  
  
 `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`합니다. 기본값은 `CComTypeInfoHolder`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|[get_Appearance](#get_appearance)|예를 들어, 단일 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 가져오려면이 메서드를 호출 합니다.|  
|[get_AutoSize](#get_autosize)|컨트롤 없습니다 될 다른 크기를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get_BackColor](#get_backcolor)|컨트롤의 배경색을 가져오려면이 메서드를 호출 합니다.|  
|[get_BackStyle](#get_backstyle)|컨트롤의 배경 스타일, 투명 또는 불투명를 가져오려면이 메서드를 호출 합니다.|  
|[get_BorderColor](#get_bordercolor)|컨트롤의 테두리 색을 가져오려면이 메서드를 호출 합니다.|  
|[get_BorderStyle](#get_borderstyle)|컨트롤의 테두리 스타일을 가져오려면이 메서드를 호출 합니다.|  
|[get_BorderVisible](#get_bordervisible)|또는 컨트롤의 테두리 표시 되는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get_BorderWidth](#get_borderwidth)|컨트롤의 테두리의 너비 (픽셀 단위)에서 가져오려면이 메서드를 호출 합니다.|  
|[get_Caption](#get_caption)|개체의 캡션에 지정 된 텍스트를 가져오면이 메서드를 호출 합니다.|  
|[get_DrawMode](#get_drawmode)|컨트롤의 그리기 모드, 예를 들어, XOR 펜 또는 색 반전를 가져오려면이 메서드를 호출 합니다.|  
|[get_DrawStyle](#get_drawstyle)|이 메서드를 호출 하는 컨트롤의 그리기 스타일을 가져올 예를 들어 실선, 파선, 또는 점선입니다.|  
|[get_DrawWidth](#get_drawwidth)|컨트롤의 그리기 메서드에서 사용 하는 픽셀 단위로 드로잉 너비를 가져오려면이 메서드를 호출 합니다.|  
|[get_Enabled](#get_enabled)|컨트롤을 사용할 수 있는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get_FillColor](#get_fillcolor)|컨트롤의 채우기 색을 가져오려면이 메서드를 호출 합니다.|  
|[get_FillStyle](#get_fillstyle)|이 메서드를 호출 하는 컨트롤의 채우기 스타일 예를 들어 단색, 투명 또는 교차 무늬 합니다.|  
|[get_Font](#get_font)|컨트롤의 글꼴 속성에 대 한 포인터를 가져오려면이 메서드를 호출 합니다.|  
|[get_ForeColor](#get_forecolor)|컨트롤의 전경색을 가져오려면이 메서드를 호출 합니다.|  
|[get_HWND](#get_hwnd)|컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다.|  
|[get_MouseIcon](#get_mouseicon)|(아이콘, 비트맵 또는 메타 파일)을 마우스 컨트롤 위에 놓을 때 표시할 그래픽의 그림 속성을 가져오려면이 메서드를 호출 합니다.|  
|[get_MousePointer](#get_mousepointer)|예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 교차, 또는 모래 시계 형식을 가져오려면이 메서드를 호출 합니다.|  
|[get_Picture](#get_picture)|(아이콘, 비트맵 또는 메타 파일)을 표시할 그래픽의 그림 속성에 대 한 포인터를 가져오려면이 메서드를 호출 합니다.|  
|[get_ReadyState](#get_readystate)|로드 또는 언로드 예를 들어 컨트롤의 준비 상태를 가져오려면이 메서드를를 호출 합니다.|  
|[get_TabStop](#get_tabstop)|컨트롤 탭은 인지 인지 여부를 나타내는 플래그를 가져오려면이 메서드를 호출 합니다.|  
|[get_Text](#get_text)|컨트롤에서 표시 되는 텍스트를 가져오려면이 메서드를 호출 합니다.|  
|[getvalid](#get_valid)|컨트롤이 유효한 인지 인지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get_Window](#get_window)|컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다. 동일 [CStockPropImpl::get_HWND](#get_hwnd)합니다.|  
|[put_Appearance](#put_appearance)|예를 들어, 단일 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 설정 하려면이 메서드를 호출 합니다.|  
|[put_AutoSize](#put_autosize)|컨트롤 없습니다 될 다른 크기를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[put_BackColor](#put_backcolor)|컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.|  
|[put_BackStyle](#put_backstyle)|컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.|  
|[put_BorderColor](#put_bordercolor)|컨트롤의 테두리 색을 설정 하려면이 메서드를 호출 합니다.|  
|[put_BorderStyle](#put_borderstyle)|컨트롤의 테두리 스타일을 설정 하려면이 메서드를 호출 합니다.|  
|[put_BorderVisible](#put_bordervisible)|또는 컨트롤의 테두리 표시 되는지 여부를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[put_BorderWidth](#put_borderwidth)|컨트롤의 테두리의 두께 설정 하려면이 메서드를 호출 합니다.|  
|[put_Caption](#put_caption)|컨트롤에서 표시할 텍스트를 설정 하려면이 메서드를 호출 합니다.|  
|[put_DrawMode](#put_drawmode)|컨트롤의 그리기 모드, 예를 들어, XOR 펜 또는 색 반전를 설정 하려면이 메서드를 호출 합니다.|  
|[put_DrawStyle](#put_drawstyle)|실선, 파선, 또는 점선 예를 들어 컨트롤의 그리기 스타일을 설정 하려면이 메서드를 호출 합니다.|  
|[put_DrawWidth](#put_drawwidth)|너비 (픽셀 단위) 컨트롤의 그리기 메서드에서 사용을 설정 하려면이 메서드를 호출 합니다.|  
|[put_Enabled](#put_enabled)|컨트롤을 사용할 수 있는지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.|  
|[put_FillColor](#put_fillcolor)|컨트롤의 채우기 색을 설정 하려면이 메서드를 호출 합니다.|  
|[put_FillStyle](#put_fillstyle)|단색, 투명 또는 교차 무늬 예를 들어 컨트롤의 채우기 스타일을 설정 하려면이 메서드를 호출 합니다.|  
|[put_Font](#put_font)|컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[put_ForeColor](#put_forecolor)|컨트롤의 전경색을 설정 하려면이 메서드를 호출 합니다.|  
|[put_HWND](#put_hwnd)|E_FAIL이 반환 됩니다.|  
|[put_MouseIcon](#put_mouseicon)|(아이콘, 비트맵 또는 메타 파일)을 마우스 컨트롤 위에 놓을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[put_MousePointer](#put_mousepointer)|예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 교차, 또는 모래 시계의 유형을 설정 하려면이 메서드를 호출 합니다.|  
|[put_Picture](#put_picture)|(아이콘, 비트맵 또는 메타 파일)을 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[put_ReadyState](#put_readystate)|로드 또는 언로드 예를 들어 컨트롤의 준비 상태를 설정 하려면이 메서드를 호출 합니다.|  
|[put_TabStop](#put_tabstop)|컨트롤 탭은 인지 인지 여부를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[put_Text](#put_text)|컨트롤에서 표시 되는 텍스트를 설정 하려면이 메서드를 호출 합니다.|  
|[putvalid](#put_valid)|컨트롤이 유효한 인지 인지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.|  
|[put_Window](#put_window)|이 메서드는 호출 [CStockPropImpl::put_HWND](#put_hwnd), E_FAIL을 반환 하는 합니다.|  
|[putref_Font](#putref_font)|참조 횟수를 사용 하 여 컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[putref_MouseIcon](#putref_mouseicon)|참조 횟수로 (아이콘, 비트맵 또는 메타 파일)을 마우스가 컨트롤 위에 있을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[putref_Picture](#putref_picture)|참조 횟수로 (아이콘, 비트맵 또는 메타 파일)를 표시 하는 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 `CStockPropImpl`제공 **배치** 및 **가져오기** 각 스톡 속성에 대 한 메서드. 이러한 메서드는 각 속성에 연결 된 데이터 멤버를 가져오거나 설정 하 고 팀에 알리고 모든 속성이 변경 될 때 컨테이너와 동기화 하는 데 필요한 코드를 제공 합니다.  
  
 Visual c + + 마법사를 통해 스톡 속성에 대 한 지원을 제공합니다. 컨트롤에 스톡 속성을 추가 하는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다.  
  
 이전 버전과 호환성을 위해 `CStockPropImpl` 노출 `get_Window` 및 `put_Window` 메서드를 호출 하기만 하면 `get_HWND` 및 `put_HWND`각각. 기본 구현은 `put_HWND` 반환 **E_FAIL** 이후 `HWND` 속성은 읽기 전용 이어야 합니다.  
  
 다음 속성에는 가지는 **putref** 구현 합니다.  
  
-   글꼴  
  
-   MouseIcon  
  
-   그림  
  
 동일한 세 가지 스톡 속성 필요한 형식으로 해당 데이터 멤버의 `CComPtr` 또는 대입 연산자를 사용 하 여 올바른 인터페이스 참조를 제공 하는 다른 클래스를 계산 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="get_appearance"></a>CStockPropImpl::get_Appearance  
 예를 들어, 단일 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnAppearance*  
 컨트롤의 그리기 스타일을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_autosize"></a>CStockPropImpl::get_AutoSize  
 컨트롤 없습니다 될 다른 크기를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbAutoSize*  
 플래그 상태를 받는 변수입니다. TRUE는 컨트롤에 다른 크기 일 수 없음을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_backcolor"></a>CStockPropImpl::get_BackColor  
 컨트롤의 배경색을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *pclrBackColor*  
 컨트롤의 배경색을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_backstyle"></a>CStockPropImpl::get_BackStyle  
 컨트롤의 배경 스타일, 투명 또는 불투명를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnBackStyle*  
 컨트롤의 배경 스타일을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_bordercolor"></a>CStockPropImpl::get_BorderColor  
 컨트롤의 테두리 색을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *pclrBorderColor*  
 컨트롤의 테두리 색을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_borderstyle"></a>CStockPropImpl::get_BorderStyle  
 컨트롤의 테두리 스타일을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnBorderStyle*  
 컨트롤의 테두리 스타일을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_bordervisible"></a>CStockPropImpl::get_BorderVisible  
 또는 컨트롤의 테두리 표시 되는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbBorderVisible*  
 플래그 상태를 받는 변수입니다. TRUE는 컨트롤의 테두리 표시 임을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_borderwidth"></a>CStockPropImpl::get_BorderWidth  
 컨트롤의 테두리의 너비를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnBorderWidth*  
 컨트롤의 테두리 너비를 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_caption"></a>CStockPropImpl::get_Caption  
 개체의 캡션에 지정 된 텍스트를 가져오면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbstrCaption*  
 컨트롤에서 표시 될 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_drawmode"></a>CStockPropImpl::get_DrawMode  
 컨트롤의 그리기 모드, 예를 들어, XOR 펜 또는 색 반전를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnDrawMode*  
 컨트롤의 그리기 모드를 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_drawstyle"></a>CStockPropImpl::get_DrawStyle  
 이 메서드를 호출 하는 컨트롤의 그리기 스타일을 가져올 예를 들어 실선, 파선, 또는 점선입니다.  
  
```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnDrawStyle*  
 컨트롤의 그리기 스타일을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_drawwidth"></a>CStockPropImpl::get_DrawWidth  
 컨트롤의 그리기 메서드에서 사용 하는 픽셀 단위로 드로잉 너비를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnDrawWidth*  
 값을 받는 컨트롤의 너비를 픽셀 단위로 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_enabled"></a>CStockPropImpl::get_Enabled  
 컨트롤을 사용할 수 있는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```  
  
### <a name="parameters"></a>매개 변수  
 `pbEnabled`  
 플래그 상태를 받는 변수입니다. TRUE는 제어를 사용할 수 있음을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_fillcolor"></a>CStockPropImpl::get_FillColor  
 컨트롤의 채우기 색을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *pclrFillColor*  
 컨트롤의 채우기 색을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_fillstyle"></a>CStockPropImpl::get_FillStyle  
 이 메서드를 호출 하는 컨트롤의 채우기 스타일 예를 들어 단색, 투명 또는 크로스해칭 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnFillStyle*  
 컨트롤의 채우기 스타일을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_font"></a>CStockPropImpl::get_Font  
 컨트롤의 글꼴 속성에 대 한 포인터를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppFont`  
 컨트롤의 글꼴 속성에 대 한 포인터를 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_forecolor"></a>CStockPropImpl::get_ForeColor  
 컨트롤의 전경색을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *pclrForeColor*  
 컨트롤의 전경 색을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_hwnd"></a>CStockPropImpl::get_HWND  
 컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `phWnd`  
 컨트롤과 연결 된 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_mouseicon"></a>CStockPropImpl::get_MouseIcon  
 (아이콘, 비트맵 또는 메타 파일)을 마우스 컨트롤 위에 놓을 때 표시할 그래픽의 그림 속성을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppPicture`  
 그래픽의 그림 속성에 대 한 포인터를 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_mousepointer"></a>CStockPropImpl::get_MousePointer  
 예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 교차, 또는 모래 시계 형식을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnMousePointer*  
 마우스 포인터의 형식을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_picture"></a>CStockPropImpl::get_Picture  
 (아이콘, 비트맵 또는 메타 파일)을 표시할 그래픽의 그림 속성에 대 한 포인터를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppPicture`  
 그림의 속성에 대 한 포인터를 받는 변수입니다. 참조 [IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762) 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_readystate"></a>CStockPropImpl::get_ReadyState  
 로드 또는 언로드 예를 들어 컨트롤의 준비 상태를 가져오려면이 메서드를를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnReadyState*  
 컨트롤의 준비 상태를 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_tabstop"></a>CStockPropImpl::get_TabStop  
 컨트롤 탭은 인지 인지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbTabStop*  
 플래그 상태를 받는 변수입니다. TRUE는 컨트롤 탭은 임을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_text"></a>CStockPropImpl::get_Text  
 컨트롤에서 표시 되는 텍스트를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbstrText*  
 컨트롤에서 표시 되는 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_valid"></a>CStockPropImpl::getvalid  
 컨트롤이 유효한 인지 인지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbValid*  
 플래그 상태를 받는 변수입니다. TRUE는 컨트롤이 유효한 지를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="get_window"></a>CStockPropImpl::get_Window  
 컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다. 동일 [CStockPropImpl::get_HWND](#get_hwnd)합니다.  
  
```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `phWnd`  
 컨트롤과 연결 된 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_appearance"></a>CStockPropImpl::put_Appearance  
 예를 들어, 단일 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```  
  
### <a name="parameters"></a>매개 변수  
 `nAppearance`  
 컨트롤에서 사용할 새 그리기 스타일입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_autosize"></a>CStockPropImpl::put_AutoSize  
 컨트롤 없습니다 될 다른 크기를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAutoSize*  
 TRUE 이면 컨트롤에는 다른 크기 일 수 없습니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_backcolor"></a>CStockPropImpl::put_BackColor  
 컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *clrBackColor*  
 새 컨트롤 배경색입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_backstyle"></a>CStockPropImpl::put_BackStyle  
 컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *nBackStyle*  
 새 컨트롤 배경 스타일입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_bordercolor"></a>CStockPropImpl::put_BorderColor  
 컨트롤의 테두리 색을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *clrBorderColor*  
 새 테두리 색입니다. OLE_COLOR 데이터 형식은 내부적으로 32 비트 정수 (long)로 표현 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_borderstyle"></a>CStockPropImpl::put_BorderStyle  
 컨트롤의 테두리 스타일을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *nBorderStyle*  
 새 테두리 스타일입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_bordervisible"></a>CStockPropImpl::put_BorderVisible  
 또는 컨트롤의 테두리 표시 되는지 여부를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```  
  
### <a name="parameters"></a>매개 변수  
 *bBorderVisible*  
 TRUE 이면 테두리를 표시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_borderwidth"></a>CStockPropImpl::put_BorderWidth  
 컨트롤의 테두리의 두께 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBorderWidth`  
 새 컨트롤의 테두리의 너비입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_caption"></a>CStockPropImpl::put_Caption  
 컨트롤에서 표시할 텍스트를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```  
  
### <a name="parameters"></a>매개 변수  
 *bstrCaption*  
 컨트롤에서 표시 될 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_drawmode"></a>CStockPropImpl::put_DrawMode  
 컨트롤의 그리기 모드, 예를 들어, XOR 펜 또는 색 반전를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nDrawMode`  
 컨트롤에 대 한 새 그리기 모드입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_drawstyle"></a>CStockPropImpl::put_DrawStyle  
 실선, 파선, 또는 점선 예를 들어 컨트롤의 그리기 스타일을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *nDrawStyle*  
 컨트롤에 대 한 새 그리기 스타일입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_drawwidth"></a>CStockPropImpl::put_DrawWidth  
 너비 (픽셀 단위) 컨트롤의 그리기 메서드에서 사용을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 *nDrawWidth*  
 컨트롤에서 사용할 새 너비의 그리기 메서드.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_enabled"></a>CStockPropImpl::put_Enabled  
 컨트롤을 사용할 수 있는지 여부를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnabled`  
 컨트롤을 사용할 수 있으면 TRUE입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_fillcolor"></a>CStockPropImpl::put_FillColor  
 컨트롤의 채우기 색을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *clrFillColor*  
 컨트롤에 대 한 새 채우기 색입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_fillstyle"></a>CStockPropImpl::put_FillStyle  
 단색, 투명 또는 교차 무늬 예를 들어 컨트롤의 채우기 스타일을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *nFillStyle*  
 컨트롤에 대 한 새 채우기 스타일입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_font"></a>CStockPropImpl::put_Font  
 컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFont`  
 컨트롤의 글꼴 속성에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_forecolor"></a>CStockPropImpl::put_ForeColor  
 컨트롤의 전경색을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *clrForeColor*  
 컨트롤의 새 전경색입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_hwnd"></a>CStockPropImpl::put_HWND  
 E_FAIL이 반환 됩니다.  
  
```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```  
  
### <a name="parameters"></a>매개 변수  
 */\*hWnd\*/*  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 E_FAIL 반환 합니다.  
  
### <a name="remarks"></a>주의  
 창 핸들은 읽기 전용 값입니다.  
  
##  <a name="put_mouseicon"></a>CStockPropImpl::put_MouseIcon  
 (아이콘, 비트맵 또는 메타 파일)을 마우스 컨트롤 위에 놓을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>매개 변수  
 `pPicture`  
 그래픽의 그림 속성에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_mousepointer"></a>CStockPropImpl::put_MousePointer  
 예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 교차, 또는 모래 시계의 유형을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```  
  
### <a name="parameters"></a>매개 변수  
 *nMousePointer*  
 마우스 포인터의 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_picture"></a>CStockPropImpl::put_Picture  
 (아이콘, 비트맵 또는 메타 파일)을 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>매개 변수  
 `pPicture`  
 그림의 속성에 대 한 포인터입니다. 참조 [IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762) 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_readystate"></a>CStockPropImpl::put_ReadyState  
 로드 또는 언로드 예를 들어 컨트롤의 준비 상태를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```  
  
### <a name="parameters"></a>매개 변수  
 *nReadyState*  
 컨트롤의 준비 상태입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_tabstop"></a>CStockPropImpl::put_TabStop  
 컨트롤 탭은 인지 인지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```  
  
### <a name="parameters"></a>매개 변수  
 *bTabStop*  
 TRUE 이면 컨트롤에 탭 정지 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_text"></a>CStockPropImpl::put_Text  
 컨트롤에서 표시 되는 텍스트를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrText`  
 컨트롤에서 표시 되는 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_valid"></a>CStockPropImpl::putvalid  
 컨트롤이 유효한 인지 인지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```  
  
### <a name="parameters"></a>매개 변수  
 *bValid*  
 TRUE 이면 컨트롤이 유효 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="put_window"></a>CStockPropImpl::put_Window  
 이 메서드는 호출 [CStockPropImpl::put_HWND](#put_hwnd), E_FAIL을 반환 하는 합니다.  
  
```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 E_FAIL 반환 합니다.  
  
### <a name="remarks"></a>주의  
 창 핸들은 읽기 전용 값입니다.  
  
##  <a name="putref_font"></a>CStockPropImpl::putref_Font  
 참조 횟수를 사용 하 여 컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFont`  
 컨트롤의 글꼴 속성에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 동일 [CStockPropImpl::put_Font](#put_font), 하지만 참조 횟수입니다.  
  
##  <a name="putref_mouseicon"></a>CStockPropImpl::putref_MouseIcon  
 참조 횟수로 (아이콘, 비트맵 또는 메타 파일)을 마우스가 컨트롤 위에 있을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>매개 변수  
 `pPicture`  
 그래픽의 그림 속성에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 동일 [CStockPropImpl::put_MouseIcon](#put_mouseicon), 하지만 참조 횟수입니다.  
  
##  <a name="putref_picture"></a>CStockPropImpl::putref_Picture  
 참조 횟수로 (아이콘, 비트맵 또는 메타 파일)를 표시 하는 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>매개 변수  
 `pPicture`  
 그림의 속성에 대 한 포인터입니다. 참조 [IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762) 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 동일 [CStockPropImpl::put_Picture](#put_picture), 하지만 참조 횟수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)

