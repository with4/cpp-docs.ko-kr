---
title: "make_unsigned 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.make_unsigned"
  - "make_unsigned"
  - "std::tr1::make_unsigned"
  - "std.make_unsigned"
  - "std::make_unsigned"
  - "type_traits/std::make_unsigned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_unsigned 클래스[TR1]"
  - "make_unsigned"
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# make_unsigned 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식을 만들거나 형식의 크기보다 크거나 같은 부호가 없는 가장 작은 형식을 만듭니다.  
  
## 구문  
  
```  
template<class T>  
    struct make_unsigned;  
  
template<class T>  
    using make_unsigned_t = typename make_unsigned<T>::type;  
  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`T`|수정할 형식입니다.|  
  
## 설명  
 형식 한정자의 인스턴스는 `is_unsigned<T>`가 true일 때 `T`인 수정된 형식을 가집니다.  그렇지 않은 경우 가장 작은 부호 있는 형식 `ST`이며, 여기서 `sizeof (T) <= sizeof (ST)`입니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)