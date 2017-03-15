---
title: "컴파일러 경고(수준 3) C4373 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4373"
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고(수준 3) C4373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'%$S': 가상 함수는 '%$pS'을\(를\) 재정의하지만, 이전 버전의 컴파일러는 매개 변수의 const\/volatile 한정자만 다른 경우에는 재정의하지 않았습니다.  
  
 응용 프로그램은 기본 클래스의 가상 메서드를 재정의하는 파생 클래스의 메서드를 포함하며, 재정의하는 메서드의 매개 변수는 가상 메서드의 매개 변수와 [const](../../cpp/const-cpp.md) 또는 [volatile](../../cpp/volatile-cpp.md) 한정자만 다릅니다. 이 경우 컴파일러는 함수 참조를 기본 클래스나 파생 클래스 중 하나의 메서드에 바인딩해야 합니다.  
  
 [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] 이전의 컴파일러 버전에서는 함수를 기본 클래스의 메서드에 바인딩한 다음 경고 메시지를 실행합니다. 이후 버전의 컴파일러에서는 `const` 또는 `volatile` 한정자를 무시하고 함수를 파생 클래스의 메서드에 바인딩한 다음 `C4373` 경고를 실행합니다. 이 두 번째 동작은 C\+\+ 표준을 준수합니다.  
  
## 예제  
 다음 코드 예제에서는 C4373 경고를 생성합니다.  
  
```  
// c4373.cpp // compile with: /c /W3 #include <stdio.h> struct Base { virtual void f(int i) { printf("base\n"); } }; struct Derived : Base { void f(const int i) {  // C4373 printf("derived\n"); } }; void main() { Derived d; Base* p = &d; p->f(1); }  
```  
  
```Output  
파생  
```