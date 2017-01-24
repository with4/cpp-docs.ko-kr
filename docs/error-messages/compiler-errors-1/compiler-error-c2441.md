---
title: "컴파일러 오류 C2441 | Microsoft Docs"
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
  - "C2441"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2441"
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2441
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : \_\_declspec\(process\)로 선언된 기호는 \/clr:pure 모드에서 const여야 합니다.  
  
 **\/clr:pure**를 사용하는 경우 변수는 기본적으로 응용 프로그램 도메인별로 지정됩니다.  **\/clr:pure**를 사용하는 경우 변수가 `__declspec(process)`으로 표시되어 있으면 한 응용 프로그램 도메인에서 변수를 수정하고 다른 응용 프로그램 도메인에서 이를 읽을 때 오류가 발생할 수 있습니다.  
  
 따라서 **\/clr:pure**를 사용하는 경우 컴파일러는 프로세스별로 변수가 `const`가 되도록 지정하여 모든 응용 프로그램 도메인에서 이 변수를 읽을 수만 있도록 합니다.  
  
 자세한 내용은 [프로세스](../../cpp/process.md) 및 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2441 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```