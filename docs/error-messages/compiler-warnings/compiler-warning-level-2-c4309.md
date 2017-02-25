---
title: "컴파일러 경고 (수준 2) C4309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4309"
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 2) C4309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion' : 상수 값이 잘립니다.  
  
 형식 변환으로 상수의 크기가 할당한 공간을 초과하므로  상수에 보다 큰 형식을 사용해야 합니다.  
  
 다음 샘플에서는 C4309 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4309.cpp  
// compile with: /W2  
int main()  
{  
   char c = 128;   // C4309  
}  
```