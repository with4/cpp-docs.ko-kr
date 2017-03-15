---
title: "컴파일러 오류 C2511 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2511"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2511"
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2511
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 오버로드된 멤버 함수가 'class'에 없습니다.  
  
 지정한 매개 변수를 사용하여 선언된 함수의 버전이 없습니다.  가능한 원인  
  
1.  함수에 잘못된 매개 변수가 전달되었습니다.  
  
2.  매개 변수가 잘못된 순서로 전달되었습니다.  
  
3.  매개 변수 이름의 철자가 잘못되었습니다.  
  
 다음 샘플에서는 C2511 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```