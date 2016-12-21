---
title: "컴파일러 오류 C2486 | Microsoft Docs"
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
  - "C2486"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2486"
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2486
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_LOCAL\_SIZE'는 'naked' 특성이 있는 함수에만 사용할 수 있습니다.  
  
 인라인 어셈블리 함수에서 `__LOCAL_SIZE` 이름은 [naked](../../cpp/naked-cpp.md) 특성을 통해 선언된 함수에 예약되어 있습니다.  
  
 다음 샘플에서는 C2486 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```