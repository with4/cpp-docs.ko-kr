---
title: "컴파일러 경고 (수준 3) C4554 | Microsoft Docs"
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
  - "C4554"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4554"
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4554
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 연산자 우선 순위에 오류가 있는지 확인하십시오. 괄호를 사용하여 우선 순위를 명확하게 지정하십시오.  
  
 다음 샘플에서는 C4554 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4554.cpp  
// compile with: /W3 /WX  
int main() {  
   int a = 0, b = 0, c = 0;  
   a = a << b + c;   // C4554  
   // probably intended (a << b) + c,  
   // but will get a << (b + c)  
}  
```