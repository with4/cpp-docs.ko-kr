---
title: "컴파일러 오류 C3168 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3168"
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 열거형의 내부 형식이 잘못되었습니다.  
  
 `enum` 형식에 대해 지정한 내부 형식이 잘못되었습니다.  내부 형식은 정수 계열 C\+\+ 형식이거나 상응하는 CLR 형식이어야 합니다.  
  
 다음 샘플에서는 C3168 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
  
 다음 샘플에서는 C3168 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3168_2.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {};  
  
__value enum E : G {e};   // C3168  
__value enum F {f};   // OK  
```