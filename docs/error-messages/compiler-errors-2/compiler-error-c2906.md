---
title: "컴파일러 오류 C2906 | Microsoft Docs"
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
  - "C2906"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2906"
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2906
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specialization' : 명시적 특수화에는 'template \<\>'가 필요합니다.  
  
 명시적 템플릿 특수화를 위한 새로운 구문을 사용해야 합니다.  
  
 다음 샘플에서는 C2906 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2906.cpp  
// compile with: /c  
template<class T> class X{};   // primary template  
class X<int> { }   // C2906  
template<> class X<int> { };   // new syntax  
```