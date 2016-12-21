---
title: "_com_ptr_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::Detach"
  - "_com_ptr_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach 메서드"
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 인터페이스 포인터를 추출하고 반환합니다.  
  
## 구문  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## 설명  
 캡슐화된 인터페이스 포인터를 추출하여 반환한 다음 캡슐화된 포인터 저장소를 **NULL**로 지웁니다.  이 작업을 통해 인터페이스 포인터의 캡슐화를 제거합니다.  원한다면 반환된 인터페이스 포인터에 **릴리스**를 호출할 수도 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)