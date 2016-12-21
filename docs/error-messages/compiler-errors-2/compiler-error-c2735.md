---
title: "컴파일러 오류 C2735 | Microsoft Docs"
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
  - "C2735"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2735"
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2735
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' 키워드를 형식 매개 변수 형식 지정자에 사용할 수 없습니다.  
  
 이 키워드는 이 컨텍스트에서 사용할 수 없습니다.  
  
 다음 샘플에서는 C2735 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```