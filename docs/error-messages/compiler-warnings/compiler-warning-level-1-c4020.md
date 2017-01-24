---
title: "컴파일러 경고 (수준 1) C4020 | Microsoft Docs"
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
  - "C4020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4020"
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 실제 매개 변수가 너무 많습니다.  
  
 함수 호출의 실제 매개 변수 개수가 함수 프로토타입 또는 정의의 정식 매개 변수 개수를 초과합니다.  컴파일러는 함수의 호출 규칙에 따라 추가 실제 매개 변수를 전달합니다.  
  
 다음 샘플에서는 C4020 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```