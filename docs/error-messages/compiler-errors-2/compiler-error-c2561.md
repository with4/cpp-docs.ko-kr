---
title: "컴파일러 오류 C2561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2561"
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 함수는 값을 반환해야 합니다.  
  
 함수가 값을 반환하도록 선언되었지만 함수 정의에 `return` 문이 포함되지 않았습니다.  
  
 이 오류는 함수 프로토타입이 잘못된 경우에 발생할 수 있습니다.  
  
1.  함수가 값을 반환하지 않는 경우에는 해당 함수를 반환 형식 [void](../../cpp/void-cpp.md)로 선언합니다.  
  
2.  함수의 모든 가능 분기가 프로토타입에 선언된 형식의 값을 반환하는지 확인합니다.  
  
3.  `AX` 레지스터에 있는 반환 값을 저장하는 인라인 어셈블리 루틴을 포함하는 C\+\+ 함수에는 return 문이 필요하기도 합니다.  `AX`에 있는 값을 임시 변수에 복사하고 함수로부터 해당 변수를 반환하십시오.  
  
 다음 샘플에서는 C2561 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```