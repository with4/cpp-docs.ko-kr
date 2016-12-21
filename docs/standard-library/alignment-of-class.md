---
title: "alignment_of 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.alignment_of"
  - "std::tr1::alignment_of"
  - "alignment_of"
  - "std.alignment_of"
  - "std::alignment_of"
  - "type_traits/std::alignment_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "alignment_of 클래스[TR1]"
  - "alignment_of"
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alignment_of 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 형식의 맞춤을 가져옵니다.  이 구조체는 [alignof](../cpp/alignof-and-alignas-cpp.md) 측면에서 구현됩니다.  맞춤 값을 쿼리만 하면 되는 경우 `alignof`를 직접 사용합니다.  태그 디스패치를 수행하는 경우처럼 정수 계열 상수가 필요한 경우 alignment\_of를 사용합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct alignment_of;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 형식 쿼리는 `Ty` 형식의 맞춤 값을 보유합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [aligned\_storage 클래스](../standard-library/aligned-storage-class.md)