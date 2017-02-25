---
title: "컴파일러 오류 C2090 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2090"
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수가 배열을 반환합니다.  
  
 함수는 배열을 반환할 수 없습니다.  대신에 배열에 대한 포인터를 반환합니다.  
  
 다음 샘플에서는 C2090 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2090.cpp  
int func1(void)[] {}   // C2090  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2090b.cpp  
// compile with: /c  
int* func2(int * i) {  
   return i;  
}  
```