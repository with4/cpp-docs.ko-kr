---
title: "Dual Interfaces and Events | Microsoft Docs"
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
  - "이중 인터페이스, 이벤트"
  - "이벤트[C++], 이중 인터페이스"
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Dual Interfaces and Events
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트 인터페이스를 이중으로 디자인 하는 것이 가능 하지만 여러 가지 좋은 디자인 이유로 그렇게 하지 않는 것입니다.  이벤트의 소스만 vtable을 통해 이벤트를 발생 시킨다는 기본적인 이유는 `Invoke`, 모두 없습니다.  이벤트 소스는 직접 vtable 메서드 호출으로 이벤트가 발생 하는 경우는 `IDispatch` 메서드는 사용 및 일반 순수 vtable 인터페이스 인터페이스 이었다는 것입니다.  이벤트 소스에 대 한 호출으로 이벤트가 발생 하면 `Invoke`vtable 메서드 사용,이 지우기 인터페이스는 dispinterface 이었다는 것입니다.  이벤트 인터페이스를 이중으로 정의 하는 경우에 클라이언트는 전혀 사용 하지 않는 인터페이스를 구현 하 게 됩니다.  
  
> [!NOTE]
>  이 인수는 이중 인터페이스를 일반적 적용 되지 않습니다.  구현 관점 이중의 광범위 한 클라이언트에서 액세스할 수 있는 인터페이스를 구현 하는 것이 빠르고 편리 하 고 완벽 하 게 지원 방법입니다.  
  
 또한 이중 이벤트 인터페이스를 방지 하는 이유입니다. Visual Basic Internet Explorer 모두를 지원 합니다.  
  
## 참고 항목  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)