---
title: "IAxWinHostWindowLic 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- No header/ATL::IAxWinHostWindowLic
- No header/ATL::CreateControlLic
- No header/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 01ff8a7205418583606cbfdb1c028d7097501e00
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic 인터페이스
이 인터페이스는 사용이 허가 된 컨트롤 및 해당 호스트 개체를 조작 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|라이센스가 있는 컨트롤을 만들고 호스트 개체에 연결 합니다.|  
|[CreateControlLicEx](#createcontrollicex)|라이센스가 있는 컨트롤을 만들고 호스트 개체에 연결 필요에 따라 이벤트 처리기를 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 `IAxWinHostWindowLic`상속 [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) 라이선스가 있는 컨트롤 만들기를 지 원하는 메서드를 추가 합니다.  
  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 이 인터페이스의 멤버를 사용 하는 샘플에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 이 인터페이스의 정의 아래와 같이 IDL 또는 c + +에서 사용할 수 있습니다.  
  
|형식 정의|파일|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h에도 포함)|  
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 라이센스가 있는 컨트롤을 만들고 초기화를로 식별 되는 창에 호스팅합니다 `hWnd`합니다.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrLic`  
 [in] 컨트롤에 대 한 라이선스 키를 포함 하는 BSTR 합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) 에 대 한 설명은 나머지 매개 변수 및 반환 값입니다.  
  
 이 메서드를 호출 하는 것 [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `IAxWinHostWindowLic::CreateControlLic`합니다.  
  
##  <a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx  
 사용이 허가 된 ActiveX 컨트롤을 만들고 초기화를 유사 하 게 지정 된 창에 호스팅합니다 [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)합니다.  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrLic`  
 [in] 컨트롤에 대 한 라이선스 키를 포함 하는 BSTR 합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) 에 대 한 설명은 나머지 매개 변수 및 반환 값입니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `IAxWinHostWindowLic::CreateControlLicEx`합니다.










