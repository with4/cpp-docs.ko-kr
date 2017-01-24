---
title: "컴파일러 경고 (수준 2) C4756 | Microsoft Docs"
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
  - "C4756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4756"
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상수 산술 연산에서 오버플로가 발생했습니다.  
  
 컴파일하는 중 상수 산술연산을 수행하는 동안 컴파일러에서 예외가 발생했습니다.  
  
 다음 샘플에서는 C4756 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4756.cpp  
// compile with: /W2 /Od  
int main()  
{  
   float f = 1e100+1e100;   // C4756  
}  
```