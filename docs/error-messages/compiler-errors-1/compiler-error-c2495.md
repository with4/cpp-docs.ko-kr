---
title: "컴파일러 오류 C2495 | Microsoft Docs"
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
  - "C2495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2495"
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 'nothrow'는 함수 선언 또는 정의에만 적용할 수 있습니다.  
  
 [nothrow](../../cpp/nothrow-cpp.md) 확장 특성은 함수 선언 또는 정의에만 적용할 수 있습니다.  
  
 다음 샘플에서는 C2495 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2495.cpp  
// compile with: /c  
__declspec(nothrow) class X {   // C2495  
   int m_data;  
} x;  
  
__declspec(nothrow) void test();   // OK  
```