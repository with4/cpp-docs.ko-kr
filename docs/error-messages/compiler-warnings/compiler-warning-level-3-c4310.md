---
title: "컴파일러 경고 (수준 3) C4310 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4310"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4310"
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 3) C4310
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

캐스팅할 때 상수 값은 잘립니다.  
  
 상수 값을 보다 작은 형식으로 캐스팅했습니다.  컴파일러에서 캐스트를 수행하지만 데이터가 잘립니다.  다음 샘플에서는 C4310 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```