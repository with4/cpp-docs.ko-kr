---
title: "컴파일러 오류 C2041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2041"
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character' 숫자가 잘못되었습니다\(기본 'number'\).  
  
 지정한 문자는 기본에 대해 유효한 숫자\(예: 8진수 또는 16진수\)가 아닙니다.  
  
 다음 샘플에서는 C2041 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```