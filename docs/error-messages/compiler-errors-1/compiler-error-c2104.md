---
title: "컴파일러 오류 C2104 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2104"
ms.assetid: 2ea78896-72a6-4901-a1fa-f33ea88ad61b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'&'비트 필드의 '&'가 무시됩니다.  
  
 비트 필드의 주소를 가져올 수 없습니다.  
  
 다음 샘플에서는 C2104 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2104.cpp  
struct X {  
   int sb : 1;  
};  
  
int main() {  
   X x;  
   &x.sb;   // C2104   
   x.sb;   // OK  
}  
```