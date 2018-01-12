---
title: "이중 인터페이스 및 이벤트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87774f0237eb42c4bd2f97185230b3c869688ca8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dual-interfaces-and-events"></a>이중 인터페이스 및 이벤트
이중으로는 이벤트 인터페이스를 디자인할 수 있지만 이렇게 하려면 하지 좋은 디자인 상의 이유로의 여러 가지가 있습니다. 기본 이유는 이벤트의 소스는 vtable 또는 통해 이벤트 발생만 `Invoke`하나만 있습니다. 이벤트 소스 직접 vtable 메서드 호출으로 이벤트를 발생 시키는 경우에 `IDispatch` 메서드를 사용 하지 않을 인터페이스 순수 vtable 인터페이스 되었는지가 명확 하 고 있습니다. 이벤트 소스에 대 한 호출으로 이벤트를 발생 시킨 경우 `Invoke`, vtable 메서드를 사용 하지 않을 있고 그것이 인터페이스는 dispinterface 되었는지가 명확 합니다. 이중 이벤트 인터페이스를 정의 하는 경우 일부 사용 되지 것입니다는 인터페이스를 구현 하는 클라이언트 필요 합니다.  
  
> [!NOTE]
>  이 인수 일반적으로 이중 인터페이스에 적용 되지 않습니다. 구현 측면에서 볼 때 이중은의 다양 한 클라이언트에 액세스할 수 있는 인터페이스를 구현 하는 빠르고 편리한, 완벽 하 게 지원 방법입니다.  
  
 이중 인터페이스; 방지 하는 이유 추가 됩니다. Internet Explorer 나 Visual Basic을 지원 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)

