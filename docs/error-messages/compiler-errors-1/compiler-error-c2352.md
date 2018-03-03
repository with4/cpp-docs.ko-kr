---
title: "컴파일러 오류 C2352 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2352
dev_langs:
- C++
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f78b68103586a7ee5b73a73b2d14e188aabc46ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2352"></a>컴파일러 오류 C2352
'class::function': 비정적 멤버 함수를 잘못 호출했습니다.  
  
 `static` 멤버 함수가 비정적 멤버 함수를 호출했습니다. 또는 비정적 멤버 함수가 클래스 외부에서 정적 함수로 호출되었습니다.  
  
 다음 샘플에서는 C2352를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2352.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1();  
   void func2();  
   static void func3() {  
      func2();   // C2352 calls nonstatic func2  
      func1();   // OK calls static func1  
   }  
};  
```  
  
 다음 샘플에서는 C2352를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2352b.cpp  
class MyClass {  
public:  
   void MyFunc() {}  
   static void MyFunc2() {}  
};  
  
int main() {  
   MyClass::MyFunc();   // C2352  
   MyClass::MyFunc2();   // OK  
}  
```