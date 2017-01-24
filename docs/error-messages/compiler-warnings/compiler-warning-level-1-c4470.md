---
title: "컴파일러 경고 (수준 1) C4470 | Microsoft Docs"
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
  - "C4470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4470"
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/clr를 지정하면 부동 소수점 제어 pragma가 무시됩니다.  
  
 부동 소수점 pragma는 다음과 같습니다.  
  
-   [fenv\_access](../../preprocessor/fenv-access.md)  
  
-   [float\_control](../../preprocessor/float-control.md)  
  
-   [fp\_contract](../../preprocessor/fp-contract.md)  
  
 이러한 pragma는 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)를 사용하는 경우 무시됩니다.  
  
 다음 샘플에서는 C4470 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4470.cpp  
// compile with: /clr /W1 /LD  
#pragma float_control(except, on)   // C4470  
```