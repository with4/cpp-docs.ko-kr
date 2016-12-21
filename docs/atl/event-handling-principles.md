---
title: "Event Handling Principles | Microsoft Docs"
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
  - "이중 인터페이스, event interfaces"
  - "이벤트 처리, advising event sources"
  - "이벤트 처리, dual event interfaces"
  - "이벤트 처리, 구현"
  - "인터페이스, event and event sink"
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event Handling Principles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 이벤트 처리 하는 일반적인 세 가지 단계입니다.  에 필요 합니다.  
  
-   개체에는 이벤트 인터페이스를 구현 합니다.  
  
-   이벤트 소스 개체가 이벤트를 수신 하려고 한다는 것을 권고 합니다.  
  
-   이벤트 소스 개체는 더 이상 이벤트를 받아야 할 때에 싱.  
  
 사용자 이벤트 인터페이스를 구현 하는 방법은 해당 형식에 따라 달라 집니다.  이벤트 인터페이스는 vtable, 이중, 또는 dispinterface에 될 수 있습니다.  인터페이스를 정의 하려면 디자이너의 이벤트 소스입니다. 이 해당 인터페이스를 구현입니다.  
  
> [!NOTE]
>  이벤트 인터페이스를 이중 수 없는 이유를 기술적 이지만 여러 가지 좋은 디자인 이유로 이중 사용할 필요가 있습니다.  그러나이 이벤트는 디자이너\/구현자에서 결정입니다  *원본*.  이벤트의 측면에서 작업 하 고 있으므로 `sink`, 가능성에 대 한 어떠한 선택 해야 허용 하지만 이중 이벤트 인터페이스를 구현 해야 합니다.  이중 인터페이스에 대 한 자세한 내용은  [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md).  
  
 이벤트 소스 어 드 바이 싱 세 단계로 나눌 수 있습니다.  
  
-   원본 개체에 대 한 쿼리  [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
-   호출  [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) 를 관심 전달 하는 이벤트 인터페이스의 IID입니다.  성공이 반환 하는지는  [특수 한](http://msdn.microsoft.com/library/windows/desktop/ms694318) 는 연결 지점 개체에 대 한 인터페이스.  
  
-   호출  [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) 전달 하는  **IUnknown** 이벤트 싱크.  성공이 반환 하는지는 `DWORD` 연결을 나타내는 쿠키입니다.  
  
 관심 받는 이벤트를 성공적으로 등록 소스 개체에 의해 발생 하는 이벤트에 따라 이벤트 인터페이스를 개체의 메서드를 호출 합니다.  더 이상 이벤트를 수신 해야 하는 경우 사용자는 쿠키 다시 연결점을 통해 전달할 수 없습니다  [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608).  이 소스와 싱크 사이의 연결이 끊어집니다.  
  
 참조 하지 않도록 주의 이벤트를 처리할 때는 순환 합니다.  
  
## 참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)