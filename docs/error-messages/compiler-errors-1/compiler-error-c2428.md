---
title: "컴파일러 오류 C2428 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2428"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2428"
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2428
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : 'bool' 형식의 피연산자에 사용할 수 없습니다.  
  
 `bool` 형식의 개체에 감소 연산자를 적용할 수 없습니다.  
  
 다음 샘플에서는 C2428 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2428.cpp  
void g(bool fFlag) {  
   --fFlag;   // C2428  
   fFlag--;   // C2428  
}  
```