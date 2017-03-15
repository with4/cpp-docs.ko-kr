---
title: "컴파일러 오류 C2299 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2299"
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# 컴파일러 오류 C2299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 동작 변경: 명시적 특수화는 복사 생성자 또는 복사 할당 연산자가 될 수 없습니다.  
  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, 이전 버전의 Visual C\+\+에서는 복사 생성자나 복사 할당 연산자의 명시적 특수화가 허용된다는 컴파일러 규칙의 결과로 발생할 수도 있습니다.  
  
 C2299를 해결하려면 복사 생성자나 할당 연산자를 템플릿 함수로 만들지 말고 클래스 형식을 사용하는 비템플릿 함수로 만들어야 합니다.  템플릿 인수를 지정하여 복사 생성자나 할당 연산자를 명시적으로 호출하는 모든 코드에서 템플릿 인수를 제거해야 합니다.  
  
 다음 샘플에서는 C2299 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```