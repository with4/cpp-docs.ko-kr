---
title: "컴파일러 오류 C2019 | Microsoft Docs"
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
  - "C2019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2019"
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전처리기 지시문이 있어야 하는데 'character'이\(가\) 있습니다.  
  
 `#` 부호 다음에 오는 문자는 전처리기 지시문의 첫 문자가 아닙니다.  
  
 다음 샘플에서는 C2019 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```