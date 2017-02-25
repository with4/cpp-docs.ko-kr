---
title: "conditional 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::conditional"
  - "std.tr1.conditional"
  - "conditional"
  - "std.conditional"
  - "std::conditional"
  - "type_traits/std::conditional"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conditional 클래스[TR1]"
  - "conditional"
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# conditional 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 조건에 따라 두 가지 형식 중 하나를 선택합니다.  
  
## 구문  
  
```  
template <bool B, class T1, class T2>  
    struct conditional;  
  
template <bool _Test, class _T1, class _T2>  
    using conditional_t = typename conditional<_Test, _T1, _T2>::type;  
```  
  
#### 매개 변수  
 `B`  
 선택된 형식을 확인하는 값입니다.  
  
 `T1`  
 B가 true인 경우의 형식 결과입니다.  
  
 `T2`  
 B가 false인 경우의 형식 결과입니다.  
  
## 설명  
 템플릿 멤버 typedef `conditional<B, T1, T2>::type`는 `B`가 `true`로 확인될 때 `T1`으로 확인되고, `B`가 `false`로 확인될 때 `T2`로 확인됩니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)