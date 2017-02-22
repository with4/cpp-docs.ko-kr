---
title: "컴파일러 오류 C2786 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2786"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2786"
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2786
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : \_\_uuidof의 피연산자가 잘못되었습니다.  
  
 [\_\_uuidof](../../cpp/uuidof-operator.md) 연산자가 첨부 GUID를 포함하는 사용자 정의 형식을 사용하거나 사용자 정의 형식의 개체를 사용합니다.  가능한 원인  
  
1.  인수가 사용자 정의 형식이 아닙니다.  
  
2.  `__uuidof`가 인수에서 GUID를 추출할 수 없습니다.  
  
 다음 샘플에서는 C2786 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```