---
title: "컴파일러 오류 C3241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3241"
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' : 이 메서드는 'interface'에 의해 정의되지 않았습니다.  
  
 함수를 명시적으로 재정의할 때 함수 시그니처는 오버로드하고 있는 함수의 선언과 정확하게 일치해야 합니다.  
  
 다음 샘플에서는 C3241 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3241.cpp  
#pragma warning(disable:4199)  
  
__interface IX12A {  
   void mf();  
};  
  
__interface IX12B {  
   void mf(int);  
};  
  
class CX12 : public IX12A, public IX12B { // C3241  
   void IX12A::mf(int);  
};  
```