---
title: "링커 도구 오류 LNK1306 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1306"
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 링커 도구 오류 LNK1306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL 진입점 함수은\(는\) 관리될 수 없습니다. 네이티브로 컴파일하십시오.  
  
 DllMain은 MSIL로 컴파일할 수 없으며 네이티브로 컴파일해야 합니다.  
  
 해결 방법:  
  
-   **\/clr**를 사용하지 말고 진입점이 포함된 파일을 컴파일합니다.  
  
-   `#pragma unmanaged` 섹션에 진입점을 배치합니다.  
  
-   자세한 내용은 다음을 참조하십시오.  
  
-   [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [관리되는, 관리되지 않는](../../preprocessor/managed-unmanaged.md)  
  
-   [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [런타임 라이브러리 동작](../../build/run-time-library-behavior.md)  
  
## 예제  
 다음 샘플에서는 LNK1306 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```