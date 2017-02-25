---
title: "컴파일러 오류 C2264 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2264"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2264"
ms.assetid: 158b72cc-cee9-4a08-bd79-b7a5955345a8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2264
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 정의 또는 선언에 오류가 있습니다. 함수가 호출되지 않습니다.  
  
 잘못된 정의 또는 선언 때문에 함수를 호출할 수 없습니다.  
  
 다음 샘플에서는 C2264 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2264.cpp  
struct C {  
   // Delete the following line to resolve.  
   operator int(int = 0){}   // incorrect declaration  
};  
  
struct D {  
   operator int(){return 0;}   // OK  
};  
  
int main() {  
   int i;  
  
   C c;  
   i = c;   // C2264  
  
   D d;  
   i = d;   // OK  
}  
```