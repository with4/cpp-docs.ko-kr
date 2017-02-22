---
title: "컴파일러 오류 C2703 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2703"
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_leave 문이 잘못되었습니다.  
  
 `__leave` 문은 `__try` 블록 내부에 있어야 합니다.  
  
 다음 샘플에서는 C2703 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2703.cpp  
int main() {  
   __leave;   // C2703  
   __try {  
      // try the following line instead  
      __leave;  
   }  
   __finally {}  
}  
```