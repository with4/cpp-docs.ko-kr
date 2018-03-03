---
title: "특성의 용도 | Microsoft Docs"
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
- attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed20c29d017527d5c2ce0b0c5ab8053fc75dc6ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="purpose-of-attributes"></a>특성의 용도
방향으로 현재는 가능 하지 c + + 언어의 기본 구조를 위반 하지 않고 확장 하는 특성입니다. 특성을 통해 공급자 (별도 Dll) 언어 기능을 동적으로 확장할 수 있습니다. 특성의 기본 목표는 간소화 구성 요소 개발자의 생산성 수준을 높여 외에도 COM 구성 요소를 작성 하는 것입니다. 특성을 적용할 수 클래스, 데이터 멤버 또는 멤버 함수 등 거의 모든 c + + 구문에 있습니다. 다음은이 새로운 기술에서 제공 하는 이점의 강조 표시입니다.  
  
-   친숙 하 고 단순한 호출 규칙을 표시합니다.  
  
-   사용 하 여 매크로 달리 디버거에서 인식 하는 코드를 삽입 합니다.  
  
-   세부적인 구현 하지 않는 기본 클래스에서 쉽게 파생 수 있습니다.  
  
-   많은 양의 COM 구성 요소와 몇 가지 간단한 특성 필요한 IDL 코드를 바꿉니다.  
  
 예를 들어 제네릭 ATL 클래스에 대 한 간단한 이벤트 싱크를 구현 하려면 적용할 수 있습니다는 [event_receiver](../windows/event-receiver.md) 특정 클래스와 같은 특성 `CMyReceiver`합니다. **event_receiver** 특성 개체 파일에 적절 한 코드를 삽입 하는 Visual c + + 컴파일러에 의해 컴파일됩니다.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 설정할 수 있습니다는 **CMyReceiver** 메서드 `handler1` 및 `handler2` 이벤트를 처리 (내장 함수를 사용 하 여 [__hook](../cpp/hook.md)) 를사용하여만들수있는이벤트원본의[event_source](../windows/event-source.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../windows/attributed-programming-concepts.md)