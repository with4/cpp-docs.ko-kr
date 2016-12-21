---
title: "_variant_t::Attach | Microsoft Docs"
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
  - "_variant_t::Attach"
  - "_variant_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach 메서드"
  - "VARIANT 개체"
  - "VARIANT 개체, 연결"
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **VARIANT** 개체를 `_variant_t` 개체에 연결합니다.  
  
## 구문  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### 매개 변수  
 *varSrc*  
 이 `_variant_t` 개체에 연결되는 **VARIANT** 개체입니다.  
  
## 설명  
 **VARIANT**를 캡슐화하여 그 소유권을 받습니다.  이 멤버 함수는 캡슐화된 기존 **VARIANT**를 해제한 다음 제공된 **VARIANT**를 복사하여 해당 **VARTYPE**를 `VT_EMPTY`로 설정하여 `_variant_t` 소멸자가 리소스만 해제하도록 합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)