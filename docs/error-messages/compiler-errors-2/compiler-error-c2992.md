---
title: "컴파일러 오류 C2992 | Microsoft Docs"
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
  - "C2992"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2992"
ms.assetid: 01b16447-43fe-4e91-9a5a-af884a166a31
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2992
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 형식 매개 변수 목록이 잘못되었거나 없습니다.  
  
 클래스 앞에 `template` 또는 **generic** 키워드가 오며 매개 변수가 없거나 잘못되었습니다.  
  
## 예제  
 다음 샘플에서는 C2992를 생성합니다.  
  
```  
// C2992.cpp // compile with: /c template <class T> struct TC1 { template <class U> struct TC2; }; template <class T>   struct TC1<T>::TC2 {};   // C2992 // OK template <class T> template <class U> struct TC1<T>::TC2 {}; // C2992 can also occur when using generics: // C2992c.cpp // compile with: /clr /c generic <class T> ref struct GC1 { generic <class U> ref struct GC2; }; generic <class T> ref struct GC1<T>::GC2 {};   // C2992 // OK generic <class T> generic <class U> ref struct GC1<T>::GC2 {};  
```