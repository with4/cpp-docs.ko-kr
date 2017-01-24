---
title: "컴파일러 오류 C2316 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2316"
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception' : 소멸자로 Catch할 수 없거나 복사 생성자에 액세스할 수 없습니다.  
  
 값별 또는 참조별 예외가 catch되었지만 복사 생성자 및\/또는 대입 연산자에 액세스할 수 없습니다.  
  
 이전 버전의 컴파일러에서는 이 코드를 사용할 수 있었지만 이제 오류가 발생합니다.  
  
## 예제  
 다음 샘플에서는 C2316을 생성합니다.  
  
```  
// C2316.cpp // compile with: /EHsc #include <stdio.h> extern "C" int printf_s(const char*, ...); struct B { public: B() {} // Delete the following line to resolve. private: // copy constructor B(const B&) { } }; void f(const B&) { } int main() { try { B aB; f(aB); } catch (B b) {   // C2316 printf_s("Caught an exception!\n"); } }  
```