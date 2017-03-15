---
title: "컴파일러 경고 (수준 1) C4561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4561"
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 1) C4561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_fastcall'이 '\/clr' 옵션과 호환되지 않으므로 '\_\_stdcall'로 변환됩니다.  
  
 [\_\_fastcall](../../cpp/fastcall.md) 함수 호출 규칙은 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션과 함께 사용할 수 없으므로  컴파일러에서 `__fastcall`에 대한 호출을 무시합니다.  이 경고를 해결하려면 **\_\_fastcall**에 대한 호출을 제거하거나 **\/clr** 없이 컴파일하십시오.  
  
 다음 샘플에서는 C4561 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```