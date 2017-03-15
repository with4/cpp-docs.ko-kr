---
title: "컴파일러 오류 C2360 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2360"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2360"
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2360
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' 초기화가 'case' 레이블에 의해 생략되었습니다.  
  
 `switch` 문에서 `identifier` 초기화를 생략할 수 있습니다.  블록에서 초기 값을 포함하는 선언을 괄호로 묶지 않으면 이 선언을 점프할 수 없습니다. 블록 내에 선언하지 않은 변수는 `switch` 문이 끝날 때까지 범위 내에 위치합니다.  
  
 다음 샘플에서는 C2360 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```