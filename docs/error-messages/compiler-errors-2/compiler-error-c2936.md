---
title: "컴파일러 오류 C2936 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2936"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2936"
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2936
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id가 글로벌 데이터 변수로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 글로벌 데이터 변수로 사용할 수 없습니다.  
  
 중괄호가 짝이 맞지 않는 경우 이 오류가 발생할 수 있습니다.  
  
 다음 샘플에서는 C2936을 생성합니다.  
  
```  
// C2936.cpp // compile with: /c template<class T> struct TC { }; int TC<int>;   // C2936 // OK struct TC2 { }; int TC2;  
```  
  
 C2936은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2936b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; int GC<int>;   // C2936 // OK ref struct GC2 {}; int GC2;  
```