---
title: "컴파일러 오류 C2292 | Microsoft Docs"
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
  - "C2292"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2292"
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2292
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 최적 case 상속 표현: 'representation1'을\(를\) 선언했으나 'representation2'이\(가\) 있어야 합니다.  
  
 [\/vmb](../../build/reference/vmb-vmg-representation-method.md)\("항상 클래스 먼저 지정" 표현\)를 포함하는 다음 코드를 컴파일하면 C2292가 발생합니다.  
  
```  
// C2292.cpp  
// compile with: /vmb  
class __single_inheritance X;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2292, X uses multiple inheritance  
```