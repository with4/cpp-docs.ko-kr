---
title: "컴파일러 오류 C3738 | Microsoft Docs"
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
  - "C3738"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3738"
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3738
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'calling\_convention': 명시적 인스턴스화의 호출 규칙은 인스턴스화되는 템플릿의 호출 규칙과 일치해야 합니다.  
  
 명시적 인스턴스화에 대한 호출 규칙은 지정하지 않는 것이 좋습니다.  이를 지정해야 하는 경우에는 호출 규칙이 일치해야 합니다.  
  
## 예제  
 다음 샘플에서는 C3738 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3738.cpp  
// compile with: /clr  
// processor: x86  
#include <stdio.h>  
template< class T >  
void f ( T arg ) {   // by default calling convention is __cdecl  
   printf ( "f: %s\n", __FUNCSIG__ );  
}  
  
template   
void __stdcall f< int > ( int arg );   // C3738  
// try the following line instead  
// void f< int > ( int arg );  
  
int main () {  
   f(1);  
   f< int > ( 1 );  
}  
```