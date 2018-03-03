---
title: "이벤트 처리 인터페이스를 구현 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9226cf2630ad18651f9bda2f154f49b5b739a433
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-the-event-handling-interface"></a>이벤트 처리 인터페이스를 구현 합니다.
ATL 사용 하면 이벤트를 처리 하는 데 필요한 세 요소 모두: 이벤트 인터페이스를 구현 하 고 이벤트 소스를 확인 하 라는 바이 이벤트 소스입니다. 수행 해야 하는 정확한 단계는 응용 프로그램의 성능 요구 사항 및 이벤트 인터페이스의 형식에 따라 달라 집니다.  
  
 ATL을 사용 하 여 인터페이스를 구현 하는 가장 일반적인 방법은 다음과 같습니다.  
  
-   사용자 지정 인터페이스에서 직접 파생 합니다.  
  
-   파생 된 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 이중 인터페이스의 형식 라이브러리에서 설명 합니다.  
  
-   파생 된 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 형식 라이브러리에서 설명 하는 dispinterface에 대 한 합니다.  
  
-   파생 된 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 런타임 시 형식 정보를 로드 하 여 효율성을 개선 하려는 경우 또는 형식 라이브러리에 설명 되지 않은 dispinterface에 대 한 합니다.  
  

 호출 하 여 이벤트 소스를 조언을 해야 사용자 지정 또는 이중 인터페이스를 구현 하는 경우 [AtlAdvise](reference/connection-point-global-functions.md#atladvise) 또는 [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)합니다. 호출에 의해 반환 된 쿠키를 추적 하기 위해 필요 합니다. 호출 [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) 연결을 끊습니다.  

  
 사용 하 여 인터페이스를 구현 하는 경우 `IDispEventImpl` 또는 `IDispEventSimpleImpl`를 호출 하 여 이벤트 소스를 조언을 해야 [IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)합니다. 호출 [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) 연결을 끊습니다.  
  
 사용 중인 경우 `IDispEventImpl` 싱크 맵에 나열 된 이벤트 소스가 권장 되며 자동으로 사용 하 여 unadvised 합성 컨트롤의 기본 클래스로 수 [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)합니다.  
  
 `IDispEventImpl` 및 `IDispEventSimpleImpl` 드립니다 쿠키를 관리 하는 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)

