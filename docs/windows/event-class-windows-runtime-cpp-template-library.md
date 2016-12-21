---
title: "Event 클래스(Windows Runtime C++ 템플릿 라이브러리) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Event"
dev_langs: 
  - "C++"
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event 클래스(Windows Runtime C++ 템플릿 라이브러리)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트를 나타냅니다.  
  
## 구문  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[Event::Event 생성자\(Windows Runtime C\+\+ 템플릿 라이브러리\)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|이벤트 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[Event::operator\= 연산자](../windows/event-operator-assign-operator.md)|현재 이벤트 인스턴스를 지정된 이벤트 참조를 할당합니다.|  
  
## 상속 계층  
 `HandleT`  
  
 `Event`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)