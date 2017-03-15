---
title: "컴파일러 오류 C2120 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2120"
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2120
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 형식에서 'void'를 사용할 수 없습니다.  
  
 `void` 형식은 선언 부분에서 다른 형식과 함께 사용됩니다.  
  
 다음 샘플에서는 C2120 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2120.cpp  
int main() {  
   void int i;   // C2120  
   int j;   // OK  
}  
```