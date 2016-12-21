---
title: "_com_ptr_t::Attach | Microsoft Docs"
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
  - "_com_ptr_t::Attach"
  - "_com_ptr_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach 메서드"
  - "COM 인터페이스, 연결 포인터"
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.  
  
## 구문  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### 매개 변수  
 `pInterface`  
 원시 인터페이스 포인터입니다.  
  
 `fAddRef`  
 **true**이면 `AddRef`가 호출됩니다.  **false**이면 `_com_ptr_t` 개체가 `AddRef`를 호출하지 않고 원시 인터페이스 포인터의 소유권을 갖습니다.  
  
## 설명  
  
-   **Attach\(** `pInterface` **\)** `AddRef`가 호출되지 않습니다.  인터페이스 소유권이 이 `_com_ptr_t` 개체에 전달됩니다.  **릴리스**는 이전에 캡슐화된 포인터의 참조 횟수를 감소시키기 위해 호출됩니다.  
  
-   **Attach\(** `pInterface` **,**  `fAddRef` **\)** `fAddRef`가 **true**이면 캡슐화된 인터페이스 포인터의 참조를 늘리기 위해 `AddRef`가 호출됩니다.  `fAddRef`가 **false**이면 이 `_com_ptr_t` 개체가 `AddRef`를 호출하지 않고 원시 인터페이스 포인터의 소유권을 갖습니다.  **릴리스**는 이전에 캡슐화된 포인터의 참조 횟수를 감소시키기 위해 호출됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)