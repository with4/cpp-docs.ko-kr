---
title: "컴파일러 오류 C2823 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2823"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2823"
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2823
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

typedef 템플릿이 잘못되었습니다.  
  
 템플릿은 [typedef](http://msdn.microsoft.com/ko-kr/cc96cf26-ba93-4179-951e-695d1f5fdcf1) 정의에 사용할 수 없습니다.  
  
 다음 샘플에서는 C2823 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```