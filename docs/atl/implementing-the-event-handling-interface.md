---
title: "Implementing the Event Handling Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 이벤트 처리"
  - "이벤트 처리, ATL"
  - "인터페이스, event and event sink"
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing the Event Handling Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL을 이용 하면 이벤트 처리에 필요한 모든 세 가지 요소: 이벤트 인터페이스를 구현 하 고 이벤트 소스 어 드 바이 싱 바이 이벤트 소스입니다.  수행 해야 하는 정확한 단계는 응용 프로그램의 성능 요구 사항 및 이벤트 인터페이스 유형에 따라 달라 집니다.  
  
 ATL을 사용 하 여 인터페이스를 구현 하는 가장 일반적인 방법은 다음과 같습니다.  
  
-   사용자 지정 인터페이스에서 직접 파생 합니다.  
  
-   파생  [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 이중 인터페이스의 형식 라이브러리에서 설명 합니다.  
  
-   파생  [IDispEventImpl](../atl/reference/idispeventimpl-class.md) dispinterfaces 형식 라이브러리에서 기술에 대 한.  
  
-   파생  [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) dispinterfaces 형식 라이브러리 또는 런타임 형식 정보 로드 하 여 효율성을 향상 시킬 때를 설명에 대 한.  
  
 사용자 지정 또는 이중 인터페이스를 구현 하는 경우 호출 하 여 이벤트 소스를 알아내도록 해야  [AtlAdvise](../Topic/AtlAdvise.md) 또는  [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md).  호출에서 직접 반환 된 쿠키를 추적 해야 합니다.  호출  [AtlUnadvise](../Topic/AtlUnadvise.md) 연결을 끊습니다.  
  
 사용 하 여 dispinterface를 구현 하는 경우 `IDispEventImpl` 또는 `IDispEventSimpleImpl`를 호출 하 여 이벤트 소스를 알아내도록 해야  [IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md).  호출  [IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) 연결을 끊습니다.  
  
 사용 하는 경우 `IDispEventImpl` 합성 컨트롤의 기본 클래스로 싱크 맵에 나열 된 이벤트 소스 가까워 unadvised 자동으로 사용 되며  [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md).  
  
 `IDispEventImpl` 및 `IDispEventSimpleImpl` 클래스를 쿠키를 관리 합니다.  
  
## 참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)