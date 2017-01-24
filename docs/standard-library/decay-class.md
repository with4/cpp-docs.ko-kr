---
title: "decay 클래스 | Microsoft Docs"
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
  - "decay"
  - "std.tr1.decay"
  - "std::tr1::decay"
  - "std.decay"
  - "std::decay"
  - "type_traits/std::decay"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decay 클래스[TR1]"
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# decay 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

값으로 전달 될 때 형식을 생성 합니다. 비참조 형식, 비상수, 비휘발성, 또는 함수 또는 배열 형식에서 형식에 대 한 포인터를 만듭니다.  
  
## 구문  
  
```  
template<class T>  
    struct decay;  
  
template<class T> using decay_t = typename decay<T>::type;  
```  
  
#### 매개 변수  
 `T`  
 수정할 형식입니다.  
  
## 설명  
 Decay 템플릿을 사용 하 여 형식 값을 인수로 통과 하는 경우 결과 형식을 생성 합니다. 템플릿 클래스 멤버 typedef `type` 는 다음과 같은 단계로 정의 된 수정 된 형식을 보관 합니다.  
  
-   `U` 형식은 `remove_reference<T>::type`으로 정의되어 있습니다.  
  
-   경우 `is_array<U>::value` 가 true 이면 수정 된 형식 `type` 는 `remove_extent<U>::type *`합니다.  
  
-   그렇지 않은 경우, `is_function<U>::value` 가 true 이면 수정 된 형식 `type` 는 `add_pointer<U>::type`합니다.  
  
-   그렇지 않은 경우 수정 된 형식 `type` 는 `remove_cv<U>::type`합니다.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)