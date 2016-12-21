---
title: "컴파일러 오류 C2153 | Microsoft Docs"
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
  - "C2153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2153"
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2153
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

16진 상수에는 16진수가 적어도 하나는 있어야 합니다.  
  
 16진 상수 0x, 0X 및 \\x는 사용할 수 없습니다.  x나 X 다음에는 16진수가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2153 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```