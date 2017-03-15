---
title: "링커 도구 경고 LNK4217 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4217"
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 링커 도구 경고 LNK4217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지역으로 정의된 'symbol' 기호를 'function' 함수로 가져왔습니다.  
  
 기호가 지역으로 정의되어 있지만 기호에 대해 [\_\_declspec\(dllimport\)](../../cpp/dllexport-dllimport.md)가 지정되었습니다.  `__declspec` 한정자를 제거하여 이 경고를 해결하십시오.  
  
 `symbol`은이미지 내에 정의된 기호 이름이며  `function`은 기호를 가져오는 함수입니다.  
  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용하여 컴파일하는 경우에는 이 경고가 표시되지 않습니다.  
  
 LNK4217은 첫 번째 모듈의 가져오기 라이브러리를 사용하여 두 번째 모듈을 컴파일해야 하는 상황에서 두 모듈을 함께 링크하려는 경우에도 발생할 수 있습니다.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 두 번째 코드 파일:  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 이러한 두 모듈을 링크하려고 하면 LNK4217이 발생합니다. 이 문제를 해결하려면 첫 번째 샘플의 가져오기 라이브러리를 사용하여 두 번째 샘플을 컴파일합니다.