---
title: "Event::operator= 연산자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 연산자"
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event::operator= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 이벤트 인스턴스를 지정된 이벤트 참조를 할당합니다.  
  
## 구문  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### 매개 변수  
 `h`  
 Rvalue\-참조 이벤트 인스턴스입니다.  
  
## 반환 값  
 현재 이벤트 인스턴스에 대한 포인터입니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Event 클래스\(Windows Runtime C\+\+ 템플릿 라이브러리\)](../windows/event-class-windows-runtime-cpp-template-library.md)