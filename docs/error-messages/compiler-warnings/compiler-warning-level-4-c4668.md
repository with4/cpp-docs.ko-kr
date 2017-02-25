---
title: "컴파일러 경고 (수준 4) C4668 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4668"
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 4) C4668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol'은\(는\) 전처리기 매크로로 정의되어 있지 않으므로 'directives'에 해당하는 '0'으로 바뀝니다.  
  
 정의하지 않은 기호를 전처리기 지시문에 사용했으므로  이 기호는 false로 계산됩니다.  기호를 정의하려면 [\#define 지시문](../../preprocessor/hash-define-directive-c-cpp.md) 또는 [\/D](../../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4668 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```