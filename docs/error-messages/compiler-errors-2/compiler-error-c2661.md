---
title: "컴파일러 오류 C2661 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2661"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2661"
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2661
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 오버로드된 함수에서 number개의 매개 변수를 사용하지 않습니다.  
  
 가능한 원인  
  
1.  함수 호출에서 실제 매개 변수가 잘못되었습니다.  
  
2.  함수 선언이 없습니다.  
  
 다음 샘플에서는 C2661 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2661.cpp  
void func( int ){}  
void func( int, int ){}  
int main() {  
   func( );   // C2661 func( void ) was not declared  
   func( 1 );   // OK func( int ) was declared  
}  
```