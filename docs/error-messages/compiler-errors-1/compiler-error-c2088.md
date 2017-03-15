---
title: "컴파일러 오류 C2088 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2088"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2088"
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2088
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 'class\-key'에 맞지 않습니다.  
  
 구조체나 공용 구조체에 대한 연산자가 정의되지 않았습니다.  이 오류는 C 코드에 대해서만 유효합니다.  
  
 다음 샘플은 C2088을 세 번 발생시킵니다.  
  
```  
// C2088.c  
struct S {  
   int m_i;   
} s;  
  
int main() {  
   int i = s * 1;   // C2088  
   struct S s2 = +s;   // C2088  
   s++;   // C2088  
}  
```