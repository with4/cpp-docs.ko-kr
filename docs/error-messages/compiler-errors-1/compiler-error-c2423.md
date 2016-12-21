---
title: "컴파일러 오류 C2423 | Microsoft Docs"
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
  - "C2423"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2423"
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2423
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'number' : 잘못된 배율입니다.  
  
 인라인 어셈블리 코드가 1, 2, 4, 8 이외의 숫자를 사용하여 레지스터의 배율을 조정합니다.  
  
 다음 샘플에서는 C2423 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2423.cpp  
// processor: x86  
int main() {  
   _asm {  
      lea EAX, [EAX*3]   // C2423  
      lea EAX, [EAX+EAX*2]   // OK  
   }  
}  
```