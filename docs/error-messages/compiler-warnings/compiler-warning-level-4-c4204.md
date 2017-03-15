---
title: "컴파일러 경고 (수준 4) C4204 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4204"
ms.assetid: 298d2880-6737-448e-b711-15572d540200
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 비상수 집합체 이니셜라이저입니다.  
  
 Microsoft 확장\(\/Ze\)을 사용하면 배열, 구조체, 공용 구조체, 클래스 등의 집합체 형식을 상수가 아닌 값으로 초기화할 수 있습니다.  
  
## 예제  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 이러한 초기화는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.