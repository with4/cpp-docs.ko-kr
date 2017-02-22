---
title: "_variant_t 관계형 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::operator=="
  - "_variant_t.operator!="
  - "_variant_t::operator!="
  - "_variant_t.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 연산자"
  - "== 연산자, 특정 Visual C++ 개체와 사용"
  - "operator !=, 관계형 연산자"
  - "operator !=, variant"
  - "operator ==, variant"
  - "operator!=, 관계형 연산자"
  - "operator!=, variant"
  - "operator==, variant"
  - "관계형 연산자, _variant_t 클래스"
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t 관계형 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 두 `_variant_t` 개체가 같음 또는 같지 않음을 비교합니다.  
  
## 구문  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### 매개 변수  
 *varSrc*  
 `_variant_t` 개체와 비교되는 **VARIANT**.  
  
 `pSrc`  
 `_variant_t` 개체와 비교되는 **VARIANT** 포인터.  
  
## 반환 값  
 비교가 수행되면 **true**가, 수행되지 않으면 **false**가 반환됩니다.  
  
## 설명  
 `_variant_t` 개체와 **VARIANT**를 비교하여 같음 또는 같지 않음을 테스트합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)