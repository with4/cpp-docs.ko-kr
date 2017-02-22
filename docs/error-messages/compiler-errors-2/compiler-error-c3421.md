---
title: "컴파일러 오류 C3421 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3421"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3421"
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 오류 C3421
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 이 클래스의 종료자는 액세스할 수 없거나 존재하지 않으므로 호출할 수 없습니다.  
  
 종료자는 암시적으로 비공개이므로 바깥쪽 형식 외부에서 호출될 수 없습니다.  
  
 자세한 내용은 [Visual C\+\+의 소멸자 및 종료자](../../misc/destructors-and-finalizers-in-visual-cpp.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3421을 생성합니다.  
  
```  
// C3421.cpp // compile with: /clr ref class A {}; ref class B { !B() {} public: ~B() {} }; int main() { A a; a.!A();   // C3421 B b; b.!B();   // C3421 }  
```