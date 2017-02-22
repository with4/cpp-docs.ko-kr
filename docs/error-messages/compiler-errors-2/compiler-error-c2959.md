---
title: "컴파일러 오류 C2959 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2959"
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제네릭 클래스 또는 함수는 템플릿의 멤버가 될 수 없습니다.  
  
 자세한 내용은 [Windows Runtime and Managed Templates](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) 및 [Generics](../../windows/generics-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2959 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```