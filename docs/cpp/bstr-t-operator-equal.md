---
title: "_bstr_t::operator = | Microsoft Docs"
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
  - "_bstr_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 연산자, 특정 Visual C++ 개체와 사용"
  - "operator =, bstr"
  - "operator=, bstr"
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 기존 `_bstr_t` 개체에 새 값을 할당합니다.  
  
## 구문  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### 매개 변수  
 *s1*  
 기존 `_bstr_t` 개체에 할당될 `_bstr_t` 개체입니다.  
  
 *s2*  
 기존 `_bstr_t` 개체에 할당될 멀티바이트 문자열입니다.  
  
 `s3`  
 기존 `_bstr_t` 개체에 할당될 유니코드 문자열입니다.  
  
 `var`  
 기존 `_variant_t` 개체에 할당될 `_bstr_t` 개체입니다.  
  
 **Microsoft 전용 종료**  
  
## 예제  
 `operator=`를 사용하는 예제는 [\_bstr\_t::Assign](../cpp/bstr-t-assign.md)을 참조하십시오.  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)