---
title: "컴파일러 오류 C2362 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2362"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2362"
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2362
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' 초기화가 'goto label'에 의해 생략되었습니다.  
  
 [\/Za](../../build/reference/za-ze-disable-language-extensions.md)를 사용하여 컴파일할 때 레이블로 점프하면 식별자를 초기화할 수 없습니다.  
  
 블록에서 초기 값을 포함하는 선언을 괄호로 묶지 않았거나 변수를 아직 초기화하지 않았다면 선언을 점프할 수 없습니다.  
  
 다음 샘플에서는 C2326 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```