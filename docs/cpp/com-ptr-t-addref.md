---
title: "_com_ptr_t::AddRef | Microsoft Docs"
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
  - "_com_ptr_t::AddRef"
  - "_com_ptr_t.AddRef"
  - "AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef 메서드[C++], 인터페이스 포인터"
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::AddRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 인터페이스 포인터에 대해 **IUnknown**의 멤버 함수 `AddRef`를 호출합니다.  
  
## 구문  
  
```  
  
void AddRef( );  
  
```  
  
## 설명  
 캡슐화된 인터페이스 포인터에 대해 `IUnknown::AddRef`를 호출하여 포인터가 **NULL**인 경우 `E_POINTER` 오류를 발생시킵니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)