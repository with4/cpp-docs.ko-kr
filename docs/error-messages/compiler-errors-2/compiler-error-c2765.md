---
title: "컴파일러 오류 C2765 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2765"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2765"
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2765
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 템플릿의 명시적 특수화는 기본 인수를 가질 수 없습니다.  
  
 함수 템플릿의 명시적 특수화에는 기본 인수를 사용할 수 없습니다.  자세한 내용은 [Explicit Specialization of Function Templates](../../cpp/explicit-specialization-of-function-templates.md)를 참조하십시오.  
  
 다음 샘플에서는 C2765 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2765.cpp  
template<class T> void f(T t) {};  
  
template<> void f<char>(char c = 'a') {}   // C2765  
// try the following line instead  
// template<> void f<char>(char c) {}  
```