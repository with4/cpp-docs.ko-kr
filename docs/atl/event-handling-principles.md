---
title: "이벤트 처리 원칙 (ATL) | Microsoft Docs"
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
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6ec61751e16bd67686a983b43c79fea138b3fa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-principles"></a>이벤트 처리 원리
모든 이벤트를 처리할 일반적인 세 가지 단계가 있습니다. 해야 합니다.  
  
-   개체에 이벤트 인터페이스를 구현 합니다.  
  
-   개체 이벤트를 수신 하려는 이벤트 소스 하시기 바랍니다.  
  
-   개체가 더 이상 필요 없는 이벤트를 수신할 때 이벤트 소스가 unadvise 합니다.  
  
 이벤트 인터페이스를 구현 하는 방법은 해당 유형에 따라 달라 집니다. 이벤트 인터페이스는 vtable, 이중, 또는 dispinterface 수 있습니다. 이벤트 소스의; 인터페이스를 정의 하려면 디자이너가 가 해당 인터페이스를 구현할 수 있습니다.  
  
> [!NOTE]
>  이벤트 인터페이스를 이중 수 없는 없는 기술적인 이유가 있지만, 이중 사용을 방지 하는 것이 좋은 디자인 이유의 여러 가지가 있습니다. 그러나이 이벤트의 디자이너/구현 자가 결정 *소스*합니다. 이벤트의 관점에서 작업 이므로 `sink`, 선택한 모든 없을 수 있습니다 가능성에 대 한 허용 하지만 이중 인터페이스를 구현 하도록 해야 합니다. 이중 인터페이스에 대 한 자세한 내용은 참조 하십시오. [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)합니다.  
  
 이벤트 소스를 알리는 수로 세분화 3 단계:  
  
-   원본 개체에 대 한 쿼리 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)합니다.  
  
-   호출 [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) 관심 이벤트 인터페이스의 IID를 전달 합니다. 성공이 반환 됩니다는 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) 연결 지점 개체의 인터페이스입니다.  
  
-   호출 [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) 전달는 **IUnknown** 이벤트 싱크의 합니다. 성공이 반환 됩니다는 `DWORD` 연결을 나타내는 쿠키입니다.  
  
 이벤트를 수신에 관심을 가져를 성공적으로 등록 한 후 개체의 이벤트 인터페이스에 대 한 메서드는 소스 개체에 의해 발생 하는 이벤트에 따라 호출 됩니다. 통해 연결 지점으로 쿠키를 전달할 수를 더 이상 이벤트를 수신 해야 하는 경우 [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608)합니다. 이 소스와 싱크 간의 연결을 중단 됩니다.  
  
 참조 되지 않도록 주의 해야 할 때 이벤트를 처리 주기 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)

