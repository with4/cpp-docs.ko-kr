---
title: "컴파일러 오류 C2287 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2287"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2287"
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2287
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 상속 표현: 'representation1'이\(가\) 필수 'representation2'보다 덜 일반적입니다.  
  
 클래스가 필수 표현보다 간단한 표현을 사용하여 선언되었습니다.  
  
 다음 샘플에서는 C2287 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2287.cpp  
// compile with: /vmg /c  
class __single_inheritance X;  
class __single_inheritance Y;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2287  X uses multiple inheritance  
struct Y : A { };  // OK  
```