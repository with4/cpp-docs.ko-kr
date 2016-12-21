---
title: "컴파일러 경고 (수준 2) C4307 | Microsoft Docs"
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
  - "C4307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4307"
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 정수 계열 상수 오버플로입니다.  
  
 연산자를 사용한 식에 할당된 공간에 정수 계열 상수 오버플로가 발생했으므로  상수에 보다 큰 형식을 사용해야 합니다.  **signed int**는 부호를 표현하는 데 1비트를 사용하므로 `unsigned int`보다 작은 값을 저장합니다.  
  
 다음 샘플에서는 C4307 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4307.cpp  
// compile with: /W2  
int i = 2000000000 + 2000000000;   // C4307  
int j = (unsigned)2000000000 + 2000000000;   // OK  
  
int main()  
{  
}  
```