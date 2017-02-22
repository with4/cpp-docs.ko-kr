---
title: "컴파일러 오류 C3156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3156"
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 관리되는 또는 WinRT 형식의 지역 정의를 사용할 수 없습니다.  
  
 함수에 관리되는 또는 WinRT 클래스, 구조체 또는 인터페이스의 정의 또는 선언을 포함할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3156를 생성합니다.  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  
  
## 예제  
 다음 샘플에서는 C3156를 생성합니다.  
  
```  
// C3156_b.cpp  
// compile with: /clr:oldSyntax /c  
void f() {  
   __gc class X {};   // C3156  
   __gc class Y;   // C3156  
}  
```