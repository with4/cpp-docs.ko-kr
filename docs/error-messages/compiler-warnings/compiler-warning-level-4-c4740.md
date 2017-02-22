---
title: "컴파일러 경고 (수준 4) C4740 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4740"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4740"
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4740
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인라인 asm 코드 내부로 점프되거나 해당 코드 외부로 점프되는 경우에는 전역 최적화가 사용되지 않습니다.  
  
 `asm` 블록 내부로 점프되거나 블록 외부로 점프되는 경우에는 해당 함수에 대해 전역 최적화가 해제됩니다.  
  
 다음 샘플에서는 C4740 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```