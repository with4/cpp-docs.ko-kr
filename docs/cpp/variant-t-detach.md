---
title: "_variant_t::Detach | Microsoft Docs"
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
  - "_variant_t::Detach"
  - "_variant_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach 메서드"
  - "VARIANT 개체"
  - "VARIANT 개체, 분리"
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 **VARIANT** 개체를 이 `_variant_t` 개체에서 분리합니다.  
  
## 구문  
  
```  
  
VARIANT Detach( );  
  
```  
  
## 반환 값  
 캡슐화된 **VARIANT**입니다.  
  
## 설명  
 캡슐화된 **VARIANT**를 추출하여 반환한 다음 이 `_variant_t` 개체를 삭제하지 않고 지웁니다.  이 멤버 함수는 캡슐화에서 **VARIANT**를 제거하고, 이 `_variant_t` 개체의 **VARTYPE**을 `VT_EMPTY`로 설정합니다.  [VariantClear](http://msdn.microsoft.com/ko-kr/28741d81-8404-4f85-95d3-5c209ec13835) 함수를 호출하여 반환된 **VARIANT**를 해제하는 것은 사용자의 책임입니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)