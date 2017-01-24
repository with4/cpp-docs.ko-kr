---
title: "컴파일러 오류 C2422 | Microsoft Docs"
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
  - "C2422"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2422"
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2422
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operand'에 잘못된 세그먼트 재정의가 있습니다.  
  
 인라인 어셈블리 코드가 피연산자에서 세그먼트 재정의 연산자\(콜론\)를 잘못 사용했습니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   연산자 앞에 오는 레지스터가 세그먼트 레지스터가 아닙니다.  
  
-   연산자 앞에 오는 레지스터가 피연산자의 세그먼트 레지스터가 아닙니다.  
  
-   세그먼트 재정의 연산자가 간접 참조 연산자\(대괄호\) 내부에 표시됩니다.  
  
-   세그먼트 재정의 연산자 다음에 오는 식이 직접 피연산자 또는 메모리 피연산자가 아닙니다.  
  
 다음 샘플에서는 C2422 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```