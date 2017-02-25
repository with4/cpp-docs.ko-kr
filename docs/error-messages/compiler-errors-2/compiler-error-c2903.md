---
title: "컴파일러 오류 C2903 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2903"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2903"
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2903
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 기호가 클래스 템플릿 또는 함수 템플릿이 아닙니다.  
  
 코드에서 템플릿이 아닌 항목에 대해 명시적 인스턴스화를 시도합니다.  
  
 다음 샘플에서는 C2903을 생성합니다.  
  
```  
// C2903.cpp // compile with: /c namespace N { template<class T> class X {}; class Y {}; } void g() { N::template Y y;   // C2903 N::X<N::Y> y;   // OK }  
```  
  
 제네릭을 사용할 때도 C2903이 발생할 수 있습니다.  
  
```  
// C2903b.cpp // compile with: /clr /c namespace N { class Y {}; generic<class T> ref class Z {}; } void f() { N::generic Y y;   // C2903 N:: generic Z<int>^ z;   // OK }  
```