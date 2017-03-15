---
title: "__based 문법 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기반 주소 지정"
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __based 문법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 기반 주소 지정은 개체가 할당된\(정적 및 동적 기반 데이터\) 세그먼트를 정밀하게 제어해야 할 때 유용합니다.  
  
 32비트와 64비트 컴파일이 호환되는 유일한 주소 지정 방식은 32비트\/64비트 기반에 대해 32비트\/64비트 치환을 포함하거나 `void`를 기반으로 하는 형식을 정의하는 "포인터 기반"입니다.  
  
## 문법  
 *based\-range\-modifier*:  
 **\_\_based\(**  *base\-expression*  **\)**  
  
 *base\-expression*:  
 *based\-variablebased\-abstract\-declaratorsegment\-namesegment\-cast*  
  
 *based\-variable*:  
 *식별자*  
  
 *based\-abstract\-declarator*:  
 *abstract\-declarator*  
  
 *base\-type*:  
 *type\-name*  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [기반 포인터](../cpp/based-pointers-cpp.md)