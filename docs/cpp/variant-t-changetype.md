---
title: "_variant_t::ChangeType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::ChangeType"
  - "_variant_t.ChangeType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChangeType 메서드"
  - "VARIANT 개체"
  - "VARIANT 개체, ChangeType"
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::ChangeType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_variant_t` 개체의 형식을 지정된 **VARTYPE**으로 변경합니다.  
  
## 구문  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### 매개 변수  
 `vartype`  
 이 `_variant_t` 개체의 **VARTYPE**입니다.  
  
 `pSrc`  
 변환할 `_variant_t` 개체의 포인터입니다.  이 값이 **NULL**이면 변환이 적절하게 수행됩니다.  
  
## 설명  
 이 멤버 함수가 `_variant_t` 개체를 지정된 **VARTYPE**으로 변환합니다.  `pSrc`가 **NULL**이면 변환이 적절하게 수행되고 그렇지 않으면 이 `_variant_t` 개체가 `pSrc`에서 복사된 후 변환됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)