---
title: "컴파일러 오류 C2502 | Microsoft Docs"
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
  - "C2502"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2502"
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2502
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 기본 클래스에 액세스 한정자가 너무 많습니다.  
  
 기본 클래스에 액세스 한정자가 두 개 이상 있습니다.  액세스 한정자\(`public`, `private` 또는 `protected`\)는 하나만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2502 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2502.cpp  
// compile with: /c  
class A { };  
class B { };  
class C : private public A { };   // C2502  
  
// OK  
class D : private A {};  
class E : public A, private B {};  
```