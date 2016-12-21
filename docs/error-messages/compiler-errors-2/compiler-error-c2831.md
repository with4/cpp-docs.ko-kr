---
title: "컴파일러 오류 C2831 | Microsoft Docs"
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
  - "C2831"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2831"
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2831
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'에 기본 매개 변수를 사용할 수 없습니다.  
  
 세 연산자만 기본 매개 변수를 사용할 수 있습니다.  
  
-   [new](../../cpp/new-operator-cpp.md)  
  
-   할당 \=  
  
-   왼쪽 괄호 \(  
  
 다음 샘플에서는 C2831 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2831.cpp  
// compile with: /c  
#define BINOP <=  
class A {  
public:  
   int i;  
   int operator BINOP(int x = 1) {   // C2831  
   // try the following line instead  
   // int operator BINOP(int x) {  
      return i+x;  
   }  
};  
```