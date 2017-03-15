---
title: "컴파일러 오류 C2562 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2562"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2562"
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2562
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'void' 함수에서 값을 반환하고 있습니다.  
  
 함수가 `void`로 선언되었지만 값을 반환합니다.  
  
 이 오류는 함수 프로토타입이 잘못된 경우에 발생할 수 있습니다.  
  
 함수 선언에서 반환 형식을 지정하면 이 오류를 해결할 수 있습니다.  
  
 다음 샘플에서는 C2562 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```