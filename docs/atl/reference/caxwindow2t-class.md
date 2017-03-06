---
title: "CAxWindow2T 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAxWindow2T<TBase>
- ATL::CAxWindow2T
- CAxWindow2T
- ATL.CAxWindow2T<TBase>
- ATL.CAxWindow2T
- CAxWindow2
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: 22
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: a0724b0ea8922d1f39d8cf7ccd630068c32ea3ac
ms.lasthandoff: 02/28/2017

---
# <a name="caxwindow2t-class"></a>CAxWindow2T 클래스
이 클래스는 사용이 허가 된 ActiveX 컨트롤 호스팅에 대 한 지원 역시를 ActiveX 컨트롤을 호스트 하는 창 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>매개 변수  
 *TBase*  
 클래스를 `CAxWindowT` 파생 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|호스트 창을 만듭니다.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만듭니다. 초기화 하며 지정한 창에 호스팅합니다 및 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|창 클래스의 이름을 검색 하는 정적 메서드.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|할당 된 `HWND` 기존 `CAxWindow2T` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `CAxWindow2T`ActiveX 컨트롤을 호스팅하는 창을 조작 하기 위한 메서드를 제공 합니다. `CAxWindow2T`사용이 허가 된 ActiveX 컨트롤 호스팅에 대 한 지원을 있습니다. 제공 되는 호스팅 " **AtlAxWinLic80**"를 래핑하는 `CAxWindow2T`합니다.  
  
 클래스 `CAxWindow2` 의 특수화로 구현 되는 `CAxWindow2T` 클래스입니다. 이 특수화로 선언 됩니다.  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`멤버는 아래 설명 되어 [CAxWindow](../../atl/reference/caxwindow-class.md)합니다.  
  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 이 클래스의 멤버를 사용 하는 샘플에 대 한 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="a-namecaxwindow2ta--caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T  
 `CAxWindow2T` 개체를 생성합니다.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 기존 창의 핸들입니다.  
  
##  <a name="a-namecreatea--caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::Create  
 호스트 창을 만듭니다.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>주의  
 `CAxWindow2T::Create`호출 [CWindow::Create](../../atl/reference/cwindow-class.md#create) 와 `LPCTSTR lpstrWndClass` 제어 호스팅을 제공 하는 창 클래스에 매개 변수 설정 ( **AtlAxWinLic80**).  
  
 참조 `CWindow::Create` 에 대 한 설명은 매개 변수 및 반환 값입니다.  
  
 **참고** 0에 대 한 값으로 사용 되는 경우는 `MenuOrID` 매개 변수를 0U로 지정 해야 합니다 (기본값) 컴파일러 오류가 발생 하지 않도록 합니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CAxWindow2T::Create`합니다.  
  
##  <a name="a-namecreatecontrollica--caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::CreateControlLic  
 사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrLicKey`  
 컨트롤에 대 한 라이선스 키 라이센스가 없는 컨트롤을 만드는 경우 NULL입니다.  
  
### <a name="remarks"></a>주의  
 참조 [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) 에 대 한 설명은 나머지 매개 변수 및 반환 값입니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CAxWindow2T::CreateControlLic`합니다.  
  
##  <a name="a-namecreatecontrollicexa--caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 사용이 허가 된 ActiveX 컨트롤을 만듭니다. 초기화 하며 지정한 창에 호스팅합니다 및 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrLicKey`  
 컨트롤에 대 한 라이선스 키 라이센스가 없는 컨트롤을 만드는 경우 NULL입니다.  
  
### <a name="remarks"></a>주의  
 참조 [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) 에 대 한 설명은 나머지 매개 변수 및 반환 값입니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CAxWindow2T::CreateControlLicEx`합니다.  
  
##  <a name="a-namegetwndclassnamea--caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 창 클래스의 이름을 검색합니다.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>반환 값  
 창 클래스의 이름을 포함 하는 문자열에 대 한 포인터 ( **AtlAxWinLic80**) 라이센스가 없는 및 사용이 허가 된 ActiveX 컨트롤을 호스팅할 수입니다.  
  
##  <a name="a-nameoperatoreqa--caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T::operator =  
 할당 된 `HWND` 기존 `CAxWindow2T` 개체입니다.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 기존 창의 핸들입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)

