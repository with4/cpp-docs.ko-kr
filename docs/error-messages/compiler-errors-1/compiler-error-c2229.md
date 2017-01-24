---
title: "컴파일러 오류 C2229 | Microsoft Docs"
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
  - "C2229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2229"
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 'identifier'에 크기가 0인 잘못된 배열이 있습니다.  
  
 구조체나 비트 필드의 멤버에 크기가 0인 배열이 있으며 이 멤버가 마지막 멤버가 아닙니다.  
  
 크기가 0인 배열은 구조체의 마지막에만 올 수 있으므로 구조체를 할당할 때 배열 크기를 지정해야 합니다.  
  
 크기가 0인 배열이 구조체의 마지막 멤버가 아니면 컴파일러는 나머지 필드의 오프셋을 계산하지 못합니다.  
  
 다음 샘플에서는 C2229 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```