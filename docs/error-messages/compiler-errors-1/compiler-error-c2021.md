---
title: "컴파일러 오류 C2021 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2021"
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character'이\(가\) 아니라 지수 값이 필요합니다.  
  
 부동 소수점 상수의 지수로 사용되는 문자가 잘못된 숫자입니다.  범위 내에 있는 지수를 사용해야 합니다.  
  
## 예제  
 다음 샘플에서는 C2021 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## 예제  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```