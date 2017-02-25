---
title: "컴파일러 오류 C2092 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2092"
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'array name' 배열 요소 형식은 함수일 수 없습니다.  
  
 함수의 배열은 사용할 수 없습니다.  함수에 대한 포인터의 배열을 사용하십시오.  
  
## 예제  
 다음 샘플에서는 C2092 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2092.cpp  
typedef void (F) ();  
typedef F AT[10];   // C2092  
```  
  
## 예제  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2092b.cpp  
// compile with: /c  
typedef void (F) ();  
typedef F * AT[10];  
```