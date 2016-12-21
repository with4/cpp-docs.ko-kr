---
title: "result_of 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "result_of"
  - "std.result_of"
  - "std::result_of"
  - "type_traits/std::result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of"
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# result_of 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 인수 형식을 사용 하는 호출 가능한 형식의 반환 형식을 결정 합니다.  
  
## 구문  
  
```  
template <class Fn, class... ArgTypes>  
    struct result_of<Fn(ArgTypes...)>;  
```  
  
#### 매개 변수  
 `Fn`  
 호출 가능 형식이 쿼리입니다.  
  
 `ArgTypes`  
 형식 쿼리를 호출할 수 유형 인수 목록입니다.  
  
## 설명  
 이 템플릿을 사용 하 여의 결과 형식은 컴파일 타임에 결정 `Fn`\(`ArgTypes`\) 여기서 `Fn` 호출에 있는 형식의 인수 목록과 함께 호출 가능 형식이 `ArgTypes`합니다.`type` 템플릿 클래스의 멤버 이름을 지정의 결과 형식은 `decltype(INVOKE(declval<Fn>(), declval<ArgTypes>()...))` 경우 확인 되지 않은 식 `INVOKE(declval<Fn>(), declval<ArgTypes>()...)` 이 제대로 구성 합니다. 그렇지 않은 경우 템플릿 클래스에 멤버가 없는 `type`합니다. 형식 `Fn` 및 매개 변수 팩의 모든 형식 `ArgTypes` 완전 한 형식이 있어야 `void`, 또는 배열에 알 수 없는 바인딩.  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)