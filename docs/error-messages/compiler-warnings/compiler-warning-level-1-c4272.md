---
title: "컴파일러 경고 (수준 1) C4272 | Microsoft Docs"
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
  - "C4272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4272"
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : marked \_\_declspec\(dllimport\)입니다. 함수를 가져올 때에는 네이티브 호출 규칙을 지정해야 합니다.  
  
 [\_\_clrcall](../../cpp/clrcall.md) 호출 규칙을 사용하여 표시된 함수를 내보내면 오류가 발생합니다. `__clrcall`로 표시된 함수를 가져오려고 하면 컴파일러에서 이 경고가 발생합니다.  
  
 다음 샘플에서는 C4272 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```