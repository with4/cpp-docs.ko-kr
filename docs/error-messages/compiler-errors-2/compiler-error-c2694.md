---
title: "컴파일러 오류 C2694 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2694
dev_langs: C++
helpviewer_keywords: C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a979cf038af6cb4300519a2eae735e94e84c53a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2694"></a>컴파일러 오류 C2694
'override': 재정의 가상 함수에 기본 클래스 보다 덜 제한적인 예외 사양이 가상 멤버 함수 'base'  
  
 가상 함수 재정의 된 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 함수를 재정의 하는 것이 덜 제한적인 [예외 사양이](../../cpp/exception-specifications-throw-cpp.md)합니다.  
  
 다음 샘플에서는 C2694 오류가 생성 됩니다.  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```