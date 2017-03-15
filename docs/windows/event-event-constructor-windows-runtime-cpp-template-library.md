---
title: "Event::Event 생성자(Windows Runtime C++ 템플릿 라이브러리) | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::Event"
dev_langs: 
  - "C++"
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event::Event 생성자(Windows Runtime C++ 템플릿 라이브러리)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### 매개 변수  
 `h`  
 이벤트에 대한 핸들.  기본적으로 `h`는 `nullptr`로 초기화됩니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Event 클래스\(Windows Runtime C\+\+ 템플릿 라이브러리\)](../windows/event-class-windows-runtime-cpp-template-library.md)