---
title: "컴파일러 오류 C2792 | Microsoft Docs"
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
  - "C2792"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2792"
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2792
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super': 이 키워드 다음에 '::'이 와야 합니다.  
  
 `__super` 키워드 다음에 올 수 있는 토큰은 `::`뿐입니다.  
  
 다음 샘플에서는 C2792 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2792.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super.();   // C2792  
  
      // try the following line instead  
      // __super::mf();  
   }  
};  
```