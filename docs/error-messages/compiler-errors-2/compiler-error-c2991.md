---
title: "컴파일러 오류 C2991 | Microsoft Docs"
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
  - "C2991"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2991"
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2991
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 매개 변수 'parameter' 재정의  
  
 `parameter`의 두 가지 제네릭 또는 템플릿 정의 간에 형식 충돌이 발생했습니다. 여러 제네릭 또는 템플릿 매개 변수를 정의할 때는 동일한 형식을 사용해야 합니다.  
  
 다음 샘플에서는 C2991을 생성합니다.  
  
```  
// C2991.cpp // compile with: /c template<class T, class T> struct TC {};   // C2991 // try the following line instead // template<class T, class T2> struct TC {};  
```  
  
 C2991은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2991b.cpp // compile with: /clr /c generic<class T,class T> ref struct GC {};   // C2991 // try the following line instead // generic<class T,class T2> ref struct GC {};  
```