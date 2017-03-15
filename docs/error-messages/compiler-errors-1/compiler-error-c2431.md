---
title: "컴파일러 오류 C2431 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2431"
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'의 인덱스 레지스터가 잘못되었습니다.  
  
 ESP 레지스터의 배율이 조정되었거나 ESP 레지스터가 인덱스와 기본 레지스터 모두로 사용되었습니다.  x86 프로세서에 대한 SIB 인코딩에는 둘 중 어느 것도 사용할 수 없습니다.  
  
 다음 샘플에서는 C2431 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2431.cpp  
// processor: x86  
int main() {  
   _asm mov ax, [ESI + 2*ESP]   // C2431  
   _asm mov ax, [esp + esp]   // C2431  
}  
```