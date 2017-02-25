---
title: "Compiler Error C2355 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2355"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2355"
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compiler Error C2355
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this': 비정적 멤버 함수 또는 비정적 데이터 멤버 이니셜라이저 안에서만 참조할 수 있습니다.  
  
 `this` 포인터는 비정적 멤버 함수 또는 비정적 데이터 멤버 이니셜라이저 내에서만 유효합니다.  이 오류는 클래스 선언 외부에서 멤버 함수 정의의 클래스 범위가 제대로 정규화되지 않은 경우 발생할 수 있습니다.  또한 `this` 포인터가 클래스에 선언되지 않은 함수에서 사용되는 경우에도 오류가 발생할 수 있습니다.  
  
 이 문제를 해결하려면 멤버 함수 정의가 클래스의 멤버 함수 선언과 일치하는지, 정적으로 선언되지 않았는지 확인합니다.  데이터 멤버 이니셜라이저의 경우 데이터 멤버가 정적으로 선언되지 않았는지 확인합니다.  
  
 다음 샘플에서는 C2355를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2355.cpp  
// compile with: /c  
class MyClass {};  
MyClass *p = this;   // C2355  
  
// OK  
class MyClass2 {  
public:  
   void Test() {  
      MyClass2 *p = this;  
   }  
};  
```