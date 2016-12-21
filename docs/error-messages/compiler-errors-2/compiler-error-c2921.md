---
title: "Compiler Error C2921 | Microsoft Docs"
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
  - "C2921"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2921"
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2921
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

재정의: 'class' : 클래스 템플릿 또는 제네릭이 'type'으로 다시 선언되고 있습니다.  
  
 제네릭 또는 템플릿 클래스에 동일하지 않은 여러 선언이 있습니다.  이 오류를 해결하려면 형식에 따라 다른 이름을 사용하거나 형식 이름의 재정의를 제거하세요.  
  
 다음 샘플에서는 C2921을 생성합니다.  
  
```  
// C2921.cpp  
// compile with: /c  
template <class T> struct TC2 {};  
typedef int TC2;   // C2921  
// try the following line instead  
// typedef struct TC2<int> x;   // OK - declare a template instance   
```  
  
 C2921은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2921b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC2 {};  
typedef int GC2;   // C2921  
// try the following line instead  
// typedef ref struct GC2<int> x;  
```