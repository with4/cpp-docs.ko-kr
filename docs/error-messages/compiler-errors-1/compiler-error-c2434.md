---
title: "컴파일러 오류 C2434 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2434"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2434"
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2434
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : \_\_declspec\(process\)로 선언된 기호는 \/clr:pure 모드에서 동적으로 초기화할 수 없습니다.  
  
 **\/clr:pure**에서는 프로세스별 변수를 동적으로 초기화할 수 없습니다.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [프로세스](../../cpp/process.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2434 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```