---
title: "컴파일러 오류 C2382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2382"
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 재정의. 예외 사양이 다릅니다.  
  
 [\/Za](../../build/reference/za-ze-disable-language-extensions.md) 아래에서 이 오류는 함수 오버로드가 [예외 사양](../../cpp/exception-specifications-throw-cpp.md)에서만 시도되었음을 나타냅니다.  
  
 다음 샘플에서는 C2382를 생성합니다.  
  
```  
// C2382.cpp // compile with: /Za /c void f1(void) throw(int) {} void f1(void) throw(char) {}   // C2382 void f2(void) throw(char) {}   // OK  
```