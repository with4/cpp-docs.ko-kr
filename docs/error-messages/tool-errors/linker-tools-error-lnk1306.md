---
title: "링커 도구 오류 LNK1306 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1306
dev_langs: C++
helpviewer_keywords: LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32b6589fa5e4d7dc02ccb9a6c3157c109725b895
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1306"></a>링커 도구 오류 LNK1306  
  
> DLL 진입점 함수를 관리할 수 없습니다. 네이티브로 컴파일하십시오.  
  
`DllMain`MSIL로 컴파일할 수 없습니다. 네이티브로 컴파일해야 합니다.  
  
이 문제를 해결 하려면  
  
-   없이 진입점이 포함 된 파일을 컴파일합니다 **/clr**합니다.  
  
-   진입점에 배치 된 `#pragma unmanaged` 섹션.  
  
자세한 내용은 다음을 참조하세요.  
  
-   [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed, unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [DLL 및 Visual C++ 런타임 라이브러리 동작](../../build/run-time-library-behavior.md)  
  
## <a name="example"></a>예  
  
다음 샘플에서는 lnk1306 오류가 발생 합니다.  
  
```cpp  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```  
  
이 문제를 해결 하려면 넣지 마십시오 /clr 옵션을 사용 하거나이 파일을 컴파일하는 `#pragma` 이 예제와 같이 항목 지점을 정의 하는 관리 되지 않는 섹션에 배치 하는 지시문:  
  
```cpp  
// LNK1306fix.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
#include <windows.h>  
#pragma managed(push, off)  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
#pragma managed(pop)  
```  
