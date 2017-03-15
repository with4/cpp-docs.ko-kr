---
title: "컴파일러 오류 C2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2085"
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 정식 매개 변수 목록에 없습니다.  
  
 식별자가 함수 정의에 선언되었지만 정식 매개 변수 목록에는 선언되지 않았습니다. \(ANSI C의 경우만 해당\)  
  
 다음 샘플에서는 C2085 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 세미콜론이 없으면 `func1()`은 프로토타입이 아니라 함수 정의처럼 보이므로, `main`이 `func1()` 내에 정의되며 `main` 식별자에 대해 C2085 오류가 발생합니다.