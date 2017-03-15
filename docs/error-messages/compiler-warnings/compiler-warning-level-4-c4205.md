---
title: "컴파일러 경고 (수준 4) C4205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4205"
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 함수 범위에 정적 함수 선언이 있습니다.  
  
 Microsoft 확장\(\/Ze\)을 사용하면 **static** 함수를 다른 함수 안에 선언할 수 있습니다.  이 때 함수는 전역 범위에 지정됩니다.  
  
## 예제  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 이러한 초기화는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.