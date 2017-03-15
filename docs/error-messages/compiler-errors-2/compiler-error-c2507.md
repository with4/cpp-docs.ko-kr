---
title: "컴파일러 오류 C2507 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2507"
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 기본 클래스에 가상 한정자가 너무 많습니다.  
  
 클래스 또는 구조체가 두 번 이상 `virtual`로 선언되었습니다.  `virtual` 한정자는 기본 클래스 목록에 있는 각 클래스에 대해 하나만 표시할 수 있습니다.  
  
 다음 샘플에서는 C2507 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```