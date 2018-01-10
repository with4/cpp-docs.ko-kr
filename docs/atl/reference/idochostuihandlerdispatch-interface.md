---
title: "IDocHostUIHandlerDispatch 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs: C++
helpviewer_keywords: IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6fbd91deb1d80c49dd403e8e08cc50f5fd8c8ec3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch 인터페이스
Microsoft HTML 구문 분석 및 렌더링 엔진에 대 한 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
> [!NOTE]
>  멤버에 대 한 INet SDK 참조 항목에는 다음 표의 링크를 클릭은 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) 인터페이스입니다. `IDocHostUIHandlerDispatch`동일한 기능이 **IDocUIHostHandler**, 하는 차이 `IDocHostUIHandlerDispatch` 는 dispinterface는 반면 **IDocUIHostHandler** 는 사용자 지정 하는 인터페이스입니다.  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|MSHTML 구현에서 호출 [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115)합니다. MSHTML 모달 UI를 표시 하는 경우 라고도 합니다.|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|호스트가를 MSHTML의 데이터 개체를 바꿀 수 있도록 MSHTML에 의해 호스트에서 호출 됩니다.|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|대안을 제공 하는 호스트 수 있도록 놓기 대상으로 사용 되는 때 MSHTML에 의해 호출 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)합니다.|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|호스트의 IDispatch 인터페이스를 가져올 MSHTML에 의해 호출 됩니다.|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|MSHTML 호스트의 UI 기능을 검색합니다.|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|MSHTML는 사용자 기본 설정을 저장 하는 레지스트리 키를 반환 합니다.|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|MSHTML 해당 메뉴 및 도구 모음을 제거 하는 경우 호출 됩니다.|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|MSHTML 구현에서 호출 [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281)합니다.|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|MSHTML 구현에서 호출 [ioleinplaceactiveobject:: Onframewindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)합니다.|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|MSHTML 구현에서 호출 [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053)합니다.|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|상황에 맞는 메뉴를 표시 하려면 MSHTML에서 호출 됩니다.|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|호스트가를 MSHTML 메뉴 및 도구 모음을 바꿀 수 있습니다.|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|MSHTML에 의해 호출 때 [ioleinplaceactiveobject:: Translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) 또는 [iolecontrolsite:: Translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) 호출 됩니다.|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|호스트가 로드할 URL을 수정할 수 있도록 MSHTML에 의해 호출 됩니다.|  
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|명령 상태가 변경되었음을 호스트에 알립니다.|  
  
## <a name="remarks"></a>설명  
 호스트 메뉴, 도구 모음 및이 인터페이스를 구현 하 여 Microsoft HTML 구문 분석 및 렌더링 엔진 (MSHTML)에서 사용 하는 상황에 맞는 메뉴를 바꿀 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 아래와 같이이 인터페이스의 정의 IDL 또는 c + +로 제공 됩니다.  
  
|정의 유형|파일|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h에도 포함)|  
  
## <a name="see-also"></a>참고 항목  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)









