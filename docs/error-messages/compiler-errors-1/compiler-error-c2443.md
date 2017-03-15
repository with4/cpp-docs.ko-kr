---
title: "컴파일러 오류 C2443 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2443"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2443"
ms.assetid: 315330d5-24bc-4193-a531-0642095be58f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2443
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

피연산자 크기가 충돌합니다.  
  
 명령에서 피연산자의 크기는 동일해야 합니다.  
  
 다음 샘플에서는 C2443 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2443.cpp  
// processor: x86  
short var;  
int main() {  
   __asm xchg ax,bl   // C2443  
   __asm mov al,red   // C2443  
   __asm mov al,BYTE PTR var   // OK  
}  
```