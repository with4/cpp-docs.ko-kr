---
title: "컴파일러 오류 C3656 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3656"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3656"
ms.assetid: 88965d85-73b0-4b35-8020-0650c9c94cd8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3656
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override' : 재정의 지정자를 반복할 수 없습니다.  
  
 명시적 재정의 키워드는 한 번만 지정할 수 있습니다.  자세한 내용은 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3656 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3656.cpp  
// compile with: /clr /c  
public interface struct O {  
   int f();  
};  
  
public ref struct V : O {  
   int f() override override { return 0; }   // C3656  
   // try the following line instead  
   // int f() override { return 0; }  
};  
```