---
title: "컴파일러 오류 C2884 | Microsoft Docs"
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
  - "C2884"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2884"
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2884
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : using 선언에 의해 정의되었으나 'function' 지역 함수와 충돌합니다.  
  
 함수를 두 번 이상 정의하려고 했습니다.  첫째 정의는 지역 정의이며,  둘째 정의는 `using` 선언을 사용하여 네임스페이스로부터 수행되었습니다.  
  
 다음 샘플에서는 C2884 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```