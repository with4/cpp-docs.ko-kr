---
title: "Multiple Dual Interfaces | Microsoft Docs"
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
  - "COM_INTERFACE_ENTRY_IID macro"
  - "COM_INTERFACE_ENTRY2 macro"
  - "이중 인터페이스, exposing multiple"
  - "IDispatchImpl 클래스, multiple dual interfaces"
  - "multiple dual interfaces"
  - "multiple dual interfaces, exposing with ATL"
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multiple Dual Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이중 인터페이스 \(즉, vtable 및 후기 바인딩을 사용 하므로 클래스 C\+\+ 뿐만 아니라 스크립팅 언어 가능, 유연성\)의 장점을 결합 하려고 다중 상속의 기술로.  
  
 여러 이중 인터페이스는 단일 COM 개체에서 노출 하는 것이 가능 하지만 권장 되지 않습니다.  이중 인터페이스를 여러 개 있으면 있어야 하나만 `IDispatch` 인터페이스를 노출 합니다.  경우 인지 확인 하는 데 사용할 수 있는 기술을 저하 손실 함수 또는 향상 된 코드의 복잡성 등을 수행 합니다.  이 접근 방식을 고려 하는 개발자는 신중 하 게 장단점 비교 해야 합니다.  
  
## 단일 IDispatch 인터페이스를 노출합니다.  
 두 개 이상에서 특수화를 파생 하 여 단일 개체에서 이중 인터페이스를 여러 개 노출 하는 것이 가능 `IDispatchImpl`.  그러나 클라이언트에 대 한 쿼리를 허용 하는 경우는 `IDispatch` 인터페이스를 해야 사용는  [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) 매크로 \(또는  [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)\)의 구현에 사용 하는 기본 클래스를 지정 하려면 `IDispatch`.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/CPP/multiple-dual-interfaces_1.h)]  
  
 때문에 하나의 `IDispatch` 인터페이스를 노출만 개체를 통해 액세스할 수 있는 클라이언트는 `IDispatch` 인터페이스 메서드 또는 속성에서 다른 인터페이스에 액세스할 수 없게 되지 않습니다.  
  
## 여러 개의 이중 인터페이스는 단일 IDispatch 구현으로 결합  
 ATL 제공 하지 지원의 단일 구현으로 여러 이중 인터페이스를 결합에 대 한 `IDispatch`.  그러나 수동으로 만들기는 별도의 공용 구조체에 있는 템플릿 기반 클래스는 인터페이스를 결합 하려면 몇 가지가 알려진 `IDispatch` 인터페이스를 수행 하는 새 개체를 만들기는 `QueryInterface` 함수 또는 중첩 된 개체는 않음 기반 구현을 사용 하 여 만들는 `IDispatch` 인터페이스.  
  
 이러한 방법에는 네임 스페이스 충돌 가능성을 뿐만 아니라 코드의 복잡성 및 유지 관리 문제가 있습니다.  여러 개의 이중 인터페이스를 권장 하지 않습니다.  
  
## 참고 항목  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)