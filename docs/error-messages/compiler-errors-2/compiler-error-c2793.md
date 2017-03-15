---
title: "컴파일러 오류 C2793 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2793"
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2793
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token' : '::' 다음에 예기치 않은 토큰이 있습니다. 식별자 또는 키워드 'operator'가 필요합니다.  
  
 `__super::` 다음에 올 수 있는 토큰은 식별자 또는 `operator` 키워드입니다.  
  
 다음 샘플에서는 C2793 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C2793.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::(); // C2793  
   }  
};  
```