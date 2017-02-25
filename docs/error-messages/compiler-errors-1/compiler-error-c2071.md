---
title: "컴파일러 오류 C2071 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2071"
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 저장소 클래스가 잘못되었습니다  
  
 `identifier`가 잘못된 [저장소 클래스](../../c-language/c-storage-classes.md)를 사용하여 선언되었습니다.  식별자에 대해 둘 이상의 저장소 클래스를 지정하거나 정의가 저장소 클래스 선언과 호환되지 않는 경우 이 오류가 발생할 수 있습니다.  
  
 이 문제를 해결하려면 식별자에 적합한 저장소 클래스\(예: `static` 또는  `extern`\)를 파악한 다음 선언을 해당 클래스에 일치하도록 수정합니다.  
  
## 예제  
 다음 샘플에서는 C2071 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## 예제  
 다음 샘플에서는 C2071 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```