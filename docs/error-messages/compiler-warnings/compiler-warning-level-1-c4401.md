---
title: "컴파일러 경고 (수준 1) C4401 | Microsoft Docs"
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
  - "C4401"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4401"
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4401
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bitfield' : 멤버가 비트 필드입니다.  
  
 인라인 어셈블리 코드에서 비트 필드 멤버에 액세스하려고 합니다.  인라인 어셈블리에서는 비트 필드에 액세스할 수 없으므로 비트 필드 멤버 앞에 가장 가까운 압축 경계가 사용됩니다.  
  
 이 경고가 발생하지 않도록 하려면 인라인 어셈블리 코드에 참조를 만들기 전에 비트 필드를 적합한 형식으로 캐스팅하십시오.  다음 샘플에서는 C4401 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```