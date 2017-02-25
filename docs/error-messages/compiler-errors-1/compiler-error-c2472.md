---
title: "컴파일러 오류 C2472 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2472"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2472"
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2472
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리 코드에서는 'function'을 생성할 수 없습니다. 'message'. 혼합 이미지를 생성하려면 \/clr을 사용하여 컴파일하세요.  
  
 이 오류는 관리 코드에서 지원하지 않는 형식이 순수 CLR\(공용 언어 런타임\) 환경 내에서 사용되는 경우에 발생합니다. 오류를 해결하려면 **\/clr**을 사용하여 컴파일하세요.  
  
## 예제  
 다음 샘플에서는 C2472를 생성합니다.  
  
```  
// C2472.cpp // compile with: /clr:pure // C2472 expected #include <cstdlib> int main() { int * __ptr32 p32; int * __ptr64 p64; p32 = (int * __ptr32)malloc(4); p64 = p32; }  
```  
  
## 참고 항목  
 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)