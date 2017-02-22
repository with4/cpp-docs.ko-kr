---
title: "컴파일러 경고 (수준 3) C4357 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4357"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4357"
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 3) C4357
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'을\(를\) 생성할 때 'del' 대리자에 대한 인수 형식 목록에 있는 매개 변수 배열 인수는 무시됩니다.  
  
 `ParamArray` 특성이 무시되었고, 가변 인수를 사용하여 `function`을 호출할 수 없습니다.  
  
 다음 샘플에서는 C4357 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4357.cpp  
// compile with: /clr /W3 /c  
using namespace System;  
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357  
  
public delegate void g(int i, array<Object^>^ varargs);   // OK  
```