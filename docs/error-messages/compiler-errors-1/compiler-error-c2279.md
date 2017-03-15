---
title: "컴파일러 오류 C2279 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2279"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2279"
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2279
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 정의에는 예외 사양이 나타날 수 없습니다.  
  
 **\/Za** 옵션이 지정된 경우에는 형식 정의 선언에 [예외 사양](../../cpp/exception-specifications-throw-cpp.md)을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2279 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```