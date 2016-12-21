---
title: "ATL Event Handling Summary | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트 처리, 구현"
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Event Handling Summary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일반적으로 COM 이벤트를 처리 하는 비교적 간단한 프로세스입니다.  세 가지 주요 단계가 있습니다.  
  
-   개체에는 이벤트 인터페이스를 구현 합니다.  
  
-   이벤트 소스 개체가 이벤트를 수신 하려고 한다는 것을 권고 합니다.  
  
-   이벤트 소스 개체는 더 이상 이벤트를 받아야 할 때에 싱.  
  
## 인터페이스 구현  
 ATL을 이용해 인터페이스를 구현 하는 중 네 가지가 주  
  
|에서 파생|인터페이스 형식에 대 한 적절 한|모든 방법 \* 구현 해야|형식 라이브러리를 런타임에 필요|  
|-----------|------------------------|--------------------|-----------------------|  
|인터페이스|Vtable|예|아니요|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|이중|예|예|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|아니요|예|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|아니요|아니요|  
  
 \* 지원 ATL 클래스를 사용 하는 경우 절대로 구현 필수적인는  **IUnknown** 또는 `IDispatch` 방법을 수동으로.  
  
## 싱 및 이벤트 소스를 바이  
 조언 및 ATL 사용 하 여 이벤트 소스 바이 세 가지가 주  
  
|함수에 게 알리기|싱 함수|사용 하기에 가장 적합|쿠키를 추적 해야?|설명|  
|---------------|----------|------------------|----------------|--------|  
|[AtlAdvise](../Topic/AtlAdvise.md),  [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|[AtlUnadvise](../Topic/AtlUnadvise.md)|Vtable 또는 이중 인터페이스|예|`AtlAdvise`전역 ATL 함수가입니다.  `CComPtrBase::Advise`사용 하 여  [CComPtr](../atl/reference/ccomptr-class.md) 및  [CComQIPtr](../atl/reference/ccomqiptr-class.md).|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) 또는  [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|아니요|보다 적은 매개 변수가 `AtlAdvise` 기본 클래스를 더 많은 작업 수행 하기 때문입니다.|  
|[CComCompositeControl::AdviseSinkMap\(TRUE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|[CComCompositeControl::AdviseSinkMap\(FALSE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|합성 컨트롤에 ActiveX 컨트롤|아니요|`CComCompositeControl::AdviseSinkMap`맵 모든 엔트리를 이벤트 싱크를 권장 합니다.  동일한 함수가 항목 unadvises.  이 메서드가 자동으로 호출 되는 `CComCompositeControl` 클래스입니다.|  
|[CAxDialogImpl::AdviseSinkMap\(TRUE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|[CAxDialogImpl::AdviseSinkMap\(FALSE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|ActiveX 컨트롤 대화 상자|아니요|`CAxDialogImpl::AdviseSinkMap`조언 및 모든 ActiveX 컨트롤을 대화 상자 리소스를 unadvises.  이 자동으로 수행 됩니다.|  
  
## 참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)   
 [Supporting IDispEventImpl](../atl/supporting-idispeventimpl.md)