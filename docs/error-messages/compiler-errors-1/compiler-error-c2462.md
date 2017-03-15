---
title: "컴파일러 오류 C2462 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2462"
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'new\-expression'에 형식을 정의할 수 없습니다.  
  
 `new` 연산자의 피연산자 필드에 형식을 정의할 수 없습니다.  형식 정의를 별개의 문에 배치합니다.  
  
 다음 샘플에서는 C2462 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```