---
title: "컴파일러 경고 (수준 1) C4927 | Microsoft Docs"
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
  - "C4927"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4927"
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4927
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

변환이 잘못되었습니다. 사용자 정의 변환이 암시적으로 두 번 이상 적용되었습니다.  
  
 사용자 정의 변환이 두 번 이상 암시적으로 단일 값에 적용되었습니다. 컴파일러에서 명시적 변환을 찾지 못했지만 사용된 변환이 하나 있습니다.  
  
 다음 샘플에서는 C4927 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4927.cpp  
// compile with: /W1  
struct B  
{  
   operator int ()  
   {  
      return 0;  
   }  
};  
  
struct A  
{  
   A(int i)  
   {  
   }  
  
   /*  
   // uncomment this constructor to resolve  
   A(B b)  
   {  
   }  
   */  
};  
  
A f1( B& b)  
{  
   return A(b);  
}  
  
B& f2( B& b)  
{  
   return b;  
}  
  
A f()  
{  
   B b;  
   return A(b);   // ok  
   return f1(b);  // ok  
   return b;      // C4927  
   return B(b);   // C4927  
   return f2(b);  // C4927  
}  
  
int main()  
{  
   B b;  
   A a = b;  
   A a2(b);  
}  
```