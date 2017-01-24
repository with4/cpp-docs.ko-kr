---
title: "컴파일러 오류 C2361 | Microsoft Docs"
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
  - "C2361"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2361"
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2361
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' 초기화가 'default' 레이블에 의해 생략되었습니다.  
  
 `switch` 문에서 `identifier` 초기화를 생략할 수 있습니다.  블록에서 초기 값을 포함하는 선언을 괄호로 묶지 않으면 이 선언을 점프할 수 없습니다. 블록 내에 선언하지 않은 변수는 `switch` 문이 끝날 때까지 범위 내에 위치합니다.  
  
 다음 샘플에서는 C2361 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2361.cpp  
void func( void ) {  
   int x;  
   switch (x) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   default :   // C2361 error  
      int k = 1;  
   }  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2361b.cpp  
// compile with: /c  
void func( void ) {  
   int x = 0;  
   switch (x) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   default :  
      int k = 1;  
   }  
}  
```