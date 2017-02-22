---
title: "Purpose of Attributes | Microsoft Docs"
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
  - "attributes [C++], about attributes"
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Purpose of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특성 C\+\+ 수 없습니다 현재 방향으로 클래식 구조 언어를 확장 합니다.  특성 공급자 \(별도 Dll에 동적으로 언어 기능을 확장\)을 허용 합니다.  특성의 기본 목적은 구성 요소 개발자의 생산성 수준을 향상 하는 COM 구성 요소를 제작 하는 간단 하 게 하는 것.  특성을 적용할 수 있는 클래스, 데이터 멤버 또는 멤버 함수 같은 거의 모든 C\+\+ 구문에 있습니다.  다음의이 새로운 기술의 장점 강조입니다.  
  
-   친숙 하 고 단순한 호출 규칙을 표시합니다.  
  
-   사용 하는 매크로 달리는 디버거에서 인식할 수 있는 코드를 삽입.  
  
-   세부적인 구현 정보 없이도 기본 클래스에서 쉽게 파생을 시킬 수 있습니다.  
  
-   많은 양의 IDL 코드 필요한 COM 구성 요소와 몇 가지 간단한 특성을 대체 합니다.  
  
 예를 들어, 일반 ATL 클래스에 대 한 간단한 이벤트 싱크를 구현 하 여 적용할 수 있는  [event\_receiver](../windows/event-receiver.md) 같은 특정 클래스에 특성 `CMyReceiver`.  해당  **event\_receiver** 특성입니다 다음 개체 파일에 적절 한 코드를 삽입 합니다. Visual C\+\+ 컴파일러에 의해 컴파일됩니다.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 다음 설정할 수 있습니다의  **CMyReceiver** 메서드 `handler1` 및 `handler2` 이벤트를 처리 합니다 \(내장 함수를 사용 하 여  [\_\_hook](../cpp/hook.md)\)에서 이벤트 소스를 사용 하 여 만들 수 있습니다  [event\_source](../windows/event-source.md).  
  
## 참고 항목  
 [Concepts](../windows/attributed-programming-concepts.md)