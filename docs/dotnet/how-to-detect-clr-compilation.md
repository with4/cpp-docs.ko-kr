---
title: "방법: /clr 컴파일 감지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 컴파일러 옵션[C++], 사용 감지"
  - "컴파일, /clr 감지"
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: /clr 컴파일 감지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_MANAGED` 또는 `_M_CEE` 매크로를 사용하면 **\/clr**를 사용하여 모듈을 컴파일했는지 확인할 수 있습니다.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
 매크로에 대한 자세한 내용은 [미리 정의된 매크로](../preprocessor/predefined-macros.md)를 참조하십시오.  
  
## 예제  
  
```  
// detect_CLR_compilation.cpp  
// compile with: /clr  
#include <stdio.h>  
  
int main() {  
   #if (_MANAGED == 1) || (_M_CEE == 1)  
      printf_s("compiling with /clr\n");  
   #else  
      printf_s("compiling without /clr\n");  
   #endif  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)