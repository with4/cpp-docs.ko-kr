---
title: "컴파일러 오류 C3862 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3862"
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': \/clr:pure 또는 \/clr:safe를 지정하면 관리되지 않는 함수를 컴파일할 수 없습니다.  
  
 **\/clr:pure** 또는 **\/clr:safe**를 사용하여 컴파일하면 네티이브\(비관리\) 코드가 포함된 MSIL 전용 이미지가 생성됩니다.  따라서 `unmanaged` pragma를 **\/clr:pure** 또는 **\/clr:safe**  컴파일에 사용할 수 없습니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [관리되는, 관리되지 않는](../../preprocessor/managed-unmanaged.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3862 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```