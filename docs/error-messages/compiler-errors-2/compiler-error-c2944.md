---
title: "컴파일러 오류 C2944 | Microsoft Docs"
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
  - "C2944"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2944"
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2944
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id가 템플릿의 값 인수로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 기호 대신 템플릿 값 인수로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2944를 생성합니다.  
  
```  
// C2944.cpp // compile with: /c template<class T> class TC { }; template <int TC<int> > struct X1 { };   // C2944 template <class T > struct X2 {};  
```  
  
 C2944는 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2944b.cpp // compile with: /clr /c generic<class T> ref class GC {}; template <int GC<int> > struct X2 { };   // C2944 template <class T> struct X3 {};   // OK  
```