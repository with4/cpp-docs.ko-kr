---
title: "컴파일러 경고 (수준 1) C4731 | Microsoft Docs"
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
  - "C4731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4731"
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointer' : 'register' 프레임 포인터 레지스터가 인라인 어셈블리 코드에 의해 수정되었습니다.  
  
 프레임 포인터 레지스터를 수정했습니다.  레지스터를 인라인 어셈블리 블록이나 프레임 변수\(수정된 레지스터에 따라 지역 또는 매개 변수\)에 저장하거나 복원하지 않으면 코드가 정상적으로 작동하지 않습니다.  
  
 다음 샘플에서는 C4731 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP는 프레임 포인터\(FPO 거부됨\)이며 수정되고 있습니다.  `p`가 최근 참조된 것일 때 `EBP`에 적절하게 참조됩니다.  그러나 `EBP`는 코드에 의해 덮어쓰여지게 되므로 프로그램이 제대로 작동하지 않고 결함이 발생할 수 있습니다.