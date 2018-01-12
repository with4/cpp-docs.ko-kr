---
title: "ATL 이벤트 요약 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb863f334c00569ef849167cc39d365e0588f666
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-event-handling-summary"></a>ATL 이벤트 처리 요약
일반적으로 COM 이벤트를 처리 작업은 비교적 간단 합니다. 세 가지 주요 단계가 있습니다.  
  
-   개체에 이벤트 인터페이스를 구현 합니다.  
  
-   개체 이벤트를 수신 하려는 이벤트 소스 하시기 바랍니다.  
  
-   개체가 더 이상 필요 없는 이벤트를 수신할 때 이벤트 소스가 unadvise 합니다.  
  
## <a name="implementing-the-interface"></a>인터페이스 구현  
 다음과 같이 네 가지 주요 ATL.를 사용 하 여 인터페이스 구현  
  
|파생|인터페이스 형식에 대 한 적합 한|모든 메서드 * 구현 해야|런타임 시 형식 라이브러리가 필요|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|인터페이스|Vtable|예|아니요|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|이중|예|예|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|아니요|예|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|아니요|아니요|  
  
 \*ATL 지원 클래스를 사용 하면 있습니다은 필요가 없으며 구현는 **IUnknown** 또는 `IDispatch` 메서드 수동으로 합니다.  
  
## <a name="advising-and-unadvising-the-event-source"></a>이벤트 소스를 바이 및 확인 하 라는  
 세 가지 주요 방법으로 확인 하 라는 및 바이 ATL.를 사용 하 여 이벤트 소스  
  
|Advise 함수|Unadvise 함수|사용에 가장 적합 한|쿠키를 추적 하기 위해 해야 합니다.|설명|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|  

|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)| Vtable 또는 이중 인터페이스 | 예 | `AtlAdvise` 전역 ATL 함수입니다. `CComPtrBase::Advise`사용 하는 [CComPtr](../atl/reference/ccomptr-class.md) 및 [CComQIPtr](../atl/reference/ccomqiptr-class.md). |  

|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) 또는 [ IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)| 더 | 매개 변수가 보다 적습니다 `AtlAdvise` 이후 기본 클래스는 더 많은 작업을 수행 합니다. |  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)| 복합 컨트롤의 ActiveX 컨트롤 | 더 | `CComCompositeControl::AdviseSinkMap` 모든 항목에 지도 이벤트 싱크 조언 합니다. 동일한 기능 unadvises 항목입니다. 이 메서드는 자동으로 `CComCompositeControl` 클래스입니다. |  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)| 대화 상자에서 ActiveX 컨트롤 | 더 | `CAxDialogImpl::AdviseSinkMap` unadvises 대화 상자 리소스의 모든 ActiveX 컨트롤 및 조언 합니다. 이를 자동으로 수행 됩니다. |  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)   
 [IDispEventImpl 지원](../atl/supporting-idispeventimpl.md)

