---
title: "컴파일러 경고 (수준 1) C4747 | Microsoft Docs"
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
  - "C4747"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4747"
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4747
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 'entrypoint' 호출: DLL 진입점 및 DLL 진입점에서 접근하는 호출을 포함하는 관리 코드는 로더 잠금이 있으면 실행되지 않을 수 있습니다.  
  
 컴파일러에서 MSIL로 컴파일된 예상 DLL 진입점을 발견했습니다.  진입점이 MSIL로 컴파일된 DLL을 로드하는 동안 문제가 발생할 수 있으므로 DLL 진입점 함수를 MSIL로 컴파일하지 않는 것이 좋습니다.  
  
 자세한 내용은 [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md) 및 [링커 도구 오류 LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
1.  모듈을 **\/clr**로 컴파일하지 마십시오.  
  
2.  진입점 함수를 `#pragma unmanaged`로 표시하십시오.  
  
## 예제  
 다음 샘플에서는 C4747 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4747.cpp  
// compile with: /clr /c /W1  
// C4747 expected  
#include <windows.h>  
  
// Uncomment the following line to resolve.  
// #pragma unmanaged  
  
BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {  
   return TRUE;  
};  
```