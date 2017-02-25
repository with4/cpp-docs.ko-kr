---
title: "컴파일러 오류 C2647 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2647"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2647"
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2647
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 'type1'\('type2'에서\)을\(를\) 역참조할 수 없습니다.  
  
 pointer\-to\-member 연산자\(`->*` 또는 `.*`\)의 왼쪽 피연산자를 오른쪽 연산자와 관련된 형식으로 암시적으로 변환할 수 없습니다.  
  
 다음 샘플에서는 C2647 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2647.cpp  
class C {};  
class D {};  
  
int main() {  
   D d, *pd;  
   C c, *pc = 0;  
   int C::*pmc = 0;  
   pd->*pmc = 0;   // C2647  
   d.*pmc = 0;   // C2647  
  
   // OK  
   pc->*pmc = 0;  
   c.*pmc = 0;  
}  
```