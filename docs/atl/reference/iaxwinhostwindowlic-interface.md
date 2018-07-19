---
title: IAxWinHostWindowLic 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50d2d97aa0de61697e31c424c8185c71b06c7dd0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885583"
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
|[CreateControlLic](#createcontrollic)|사용이 허가 된 컨트롤을 만들고 호스트 개체에 연결 합니다.|  
|[CreateControlLicEx](#createcontrollicex)|사용이 허가 된 컨트롤을 만듭니다 호스트 개체에 연결 하며 필요에 따라 이벤트 처리기를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 `IAxWinHostWindowLic` 상속 [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) 사용이 허가 된 컨트롤의 만들기를 지 원하는 메서드를 추가 합니다.  
  
 참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 이 인터페이스의 멤버를 사용 하는 샘플에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 이 인터페이스의 정의 아래와 같이 IDL 또는 c + +를 사용할 수 있습니다.  
  
|정의 유형|파일|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h에도 포함)|  
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
 사용이 허가 된 컨트롤을 만들고, 초기화 및 구분 창에 호스팅합니다 `hWnd`합니다.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>매개 변수  
 *bstrLic*  
 [in] 컨트롤에 대 한 라이선스 키를 포함 하는 BSTR입니다.  
  
### <a name="remarks"></a>설명  
 참조 [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) 나머지 매개 변수 및 반환 값에 대 한 합니다.  
  
 이 메서드를 호출 하는 것 [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>예  
 참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `IAxWinHostWindowLic::CreateControlLic`합니다.  
  
##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx  
 사용이 허가 된 ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)합니다.  
  
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
 *bstrLic*  
 [in] 컨트롤에 대 한 라이선스 키를 포함 하는 BSTR입니다.  
  
### <a name="remarks"></a>설명  
 참조 [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) 나머지 매개 변수 및 반환 값에 대 한 합니다.  
  
### <a name="example"></a>예  
 참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `IAxWinHostWindowLic::CreateControlLicEx`합니다.









