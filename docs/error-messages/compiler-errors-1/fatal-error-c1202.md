---
title: "심각한 오류 C1202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1202"
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 심각한 오류 C1202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

재귀 형식 또는 함수 종속성 컨텍스트가 너무 복잡합니다.  
  
 템플릿 정의가 재귀적이거나 복잡성 제한을 초과했습니다.  
  
## 예제  
 다음 샘플에서는 C1202를 생성합니다.  
  
```  
// C1202.cpp // processor: x86 IPF template<int n> class Factorial : public Factorial<n-1>  {   // C1202 public: operator int () { return Factorial <n-1>::operator int () * n; } }; Factorial<7> facSeven;  
```  
  
## 예제  
 해결 방법:  
  
```  
// C1202b.cpp // compile with: /c template<int n> class Factorial : public Factorial<n-1> { public: operator int () { return Factorial <n-1>::operator int () * n; } }; template <> class Factorial<0> { public: operator int () { return 1; } }; Factorial<7> facSeven;  
```