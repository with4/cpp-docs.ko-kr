---
title: "컴파일러 경고 C4430 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4430"
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 C4430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 지정자가 없습니다. int로 가정합니다.참고: C\+\+에서는 기본 int를 지원하지 않습니다.  
  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, 모든 선언에서 형식을 명시적으로 지정해야 하고 int가 더 이상 가정되지 않는다는 컴파일러 규칙의 결과로 발생할 수 있습니다.  
  
 C4430은 항상 오류로서 발생합니다.  `#pragma warning` 또는 **\/wd**를 사용하여 이 경고를 해제할 수 있습니다. 자세한 내용은 [경고](../../preprocessor/warning.md) 또는 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4430 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```