---
title: "컴파일러 오류 C2932 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2932"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2932"
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2932
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id가 'identifier'의 데이터 멤버로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 데이터 멤버로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2932를 생성합니다.  
  
```  
// C2932.cpp // compile with: /c template<class T> struct TC {}; struct MyStruct { int TC<int>;   // C2932 int TC;   // OK };  
```  
  
 C2932는 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2932b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; struct MyStruct { int GC<int>;   // C2932 int GC;   // OK };  
```