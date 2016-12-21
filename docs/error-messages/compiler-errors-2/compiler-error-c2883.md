---
title: "컴파일러 오류 C2883 | Microsoft Docs"
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
  - "C2883"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2883"
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2883
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 함수 선언이 using 선언에 의해 정의된 'identifier'과\(와\) 충돌합니다.  
  
 함수를 두 번 이상 정의하려고 했습니다.  첫째 정의는 `using` 선언을 사용하여 네임스페이스로부터 수행되었으며,  둘째 정의는 지역 정의입니다.  
  
 다음 샘플에서는 C2883 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```