---
title: "_variant_t::SetString | Microsoft Docs"
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
  - "_variant_t::SetString"
  - "_variant_t.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString 메서드"
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::SetString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이 `_variant_t` 개체에 문자열을 할당합니다.  
  
## 구문  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### 매개 변수  
 `pSrc`  
 문자열에 대한 포인터입니다.  
  
## 설명  
 ANSI 문자열을 유니코드 `BSTR` 문자열로 변환하고 이 `_variant_t` 개체에 할당합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)