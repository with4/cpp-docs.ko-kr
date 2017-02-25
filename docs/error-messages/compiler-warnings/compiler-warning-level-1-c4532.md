---
title: "컴파일러 경고 (수준 1) C4532 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4532"
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 1) C4532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'continue' : 종료 처리를 수행하는 동안 \_\_finally\/finally 블록에서의 점프 동작이 정의되지 않았습니다.  
  
 컴파일러에서 다음 키워드 중 하나를 발견했습니다.  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 위와 같은 키워드로 인해 비정상 종료 동안 [\_\_finally](../../cpp/try-finally-statement.md) 또는 [finally](../../dotnet/finally.md) 블록 외부로 점프합니다.  
  
 예외가 발생하여 종료 처리기\(`__finally` 또는 finally 블록\)가 실행되면서 스택이 정리되는 동안 사용자 코드에서 `__finally` 블록이 끝나기 전에 `__finally` 블록 외부로 점프하면 동작이 정의되지 않습니다.  제어가 해제 코드로 반환되지 않으므로 예외가 제대로 처리되지 않습니다.  
  
 **\_\_finally**  블록에서 점프해야 한다면 먼저 비정상적으로 종료하는지 확인하십시오.  
  
 다음 코드에서는 C4532 경고가 발생하는 경우를 보여 줍니다. 점프문을 주석으로 처리하여 경고를 해결하십시오.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```