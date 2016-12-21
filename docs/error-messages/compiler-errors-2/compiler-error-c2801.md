---
title: "컴파일러 오류 C2801 | Microsoft Docs"
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
  - "C2801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2801"
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'은\(는\) 정적 멤버가 아니어야 합니다.  
  
 다음 연산자는 비정적 멤버로서만 오버로드할 수 있습니다.  
  
-   할당 연산자 `=`  
  
-   클래스 멤버 액세스 `->`  
  
-   첨자 `[]`  
  
-   함수 호출 `()`  
  
 C2801은 다음과 같은 원인으로 발생할 수 있습니다.  
  
-   오버로드된 연산자가 클래스, 구조체 또는 공용 구조체 멤버가 아닙니다.  
  
-   오버로드된 연산자가 `static`으로 선언되었습니다.  
  
-   다음 샘플에서는 C2801 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```