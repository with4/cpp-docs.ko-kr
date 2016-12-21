---
title: "컴파일러 경고 (수준 1) C4090 | Microsoft Docs"
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
  - "C4090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4090"
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : 'modifier' 한정자가 서로 다릅니다.  
  
 작업에 사용되는 변수는 지정된 한정자로 정의되어 있으며 컴파일러에서 검색하지 않으면 이 변수를 수정할 수 없습니다.  이 식은 수정되지 않은 상태로 컴파일됩니다.  
  
 이 경고는 **const** 또는 `volatile`을 가리키도록 선언되지 않은 포인터에 **const** 또는 `volatile` 항목에 대한 포인터를 할당하는 경우에 발생할 수 있습니다.  
  
 이 경고는 C 프로그램에 대해 발생합니다.  C\+\+ 프로그램에서 컴파일러는 [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md) 오류를 발생시킵니다.  
  
 다음 샘플에서는 C4090 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4090.c  
// compile with: /W1  
int *volatile *p;  
int *const *q;  
int **r;  
  
int main() {  
   p = q;   // C4090  
   p = r;  
   q = p;   // C4090  
   q = r;  
   r = p;   // C4090  
   r = q;   // C4090  
}  
```