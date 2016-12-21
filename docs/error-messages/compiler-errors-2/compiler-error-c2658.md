---
title: "컴파일러 오류 C2658 | Microsoft Docs"
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
  - "C2658"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2658"
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2658
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 익명 구조체\/공용 구조체에서 다시 정의했습니다.  
  
 두 개의 익명 구조체 또는 공용 구조체에 식별자는 동일하지만 형식이 각기 다른 멤버 선언이 포함되었습니다.  [\/Za](../../build/reference/za-ze-disable-language-extensions.md)에서는 식별자와 형식이 동일한 멤버에 대해 이 오류가 발생하기도 합니다.  
  
 다음 샘플에서는 C2658 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```