---
title: "컴파일러 오류 C3207 | Microsoft Docs"
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
  - "C3207"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3207"
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3207
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 'arg'에 대한 템플릿 인수가 잘못되었습니다. 클래스 템플릿이 필요합니다.  
  
 템플릿 함수가 템플릿 인수를 사용하도록 정의되어 있습니다. 그러나 템플릿 형식 인수가 전달되었습니다.  
  
 다음 샘플에서는 C3207을 생성합니다.  
  
```  
// C3207.cpp template <template <class T> class TT> void f(){} template <class T> struct S { }; void f1() { f<S<int> >();   // C3207 // try the following line instead // f<S>(); }  
```