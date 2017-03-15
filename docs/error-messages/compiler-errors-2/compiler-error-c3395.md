---
title: "컴파일러 오류 C3395 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3395"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3395"
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3395
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : \_\_declspec\(dllexport\)를 \_\_clrcall 호출 규칙이 있는 함수에 적용할 수 없습니다.  
  
 `__declspec(dllexport)`과 [\_\_clrcall](../../cpp/clrcall.md)이 서로 다른 형식입니다.  자세한 내용은 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)을 참조하십시오.  
  
 다음 샘플에서는 C3395 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```