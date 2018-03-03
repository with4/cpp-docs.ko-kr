---
title: "컴파일러 오류 C2864 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2864
dev_langs:
- C++
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b463e8036b8bf452729ddfe11dea73aa9aae3a3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2864"></a>컴파일러 오류 C2864
'variable' : in-class initializer를 사용하는 정적 데이터 멤버는 비휘발성 const 정수 계열 형식이어야 합니다.  
  
 `static`, `volatile`가 아니거나 정수 계열 형식이 아닌 것으로 정의된 `const` 데이터 멤버를 초기화하려면 멤버 정의 문을 사용합니다. 그러한 멤버는 선언에서 초기화할 수 없습니다.  
  
 이 샘플에서는 c 2864를 생성합니다.  
  
```  
// C2864.cpp  
// compile with: /c  
class B  {  
private:  
   int a = 3;   // OK   
   static int b = 3;   // C2864  
   volatile static int c = 3;   // C2864  
   volatile static const int d = 3;   // C2864  
   const static long long e = 3;   // OK  
   static const double f = 3.33;   // C2864  
};  
```  
  
 이 샘플에서는 C2864를 수정하는 방법을 보여 줍니다.  
  
```  
// C2864b.cpp  
// compile with: /c  
class C  {  
private:  
   int a = 3;  
   static int b; // = 3; C2864  
   volatile static int c; // = 3; C2864  
   volatile static const int d; // = 3; C2864  
   static const long long e = 3;  
   static const double f; // = 3.33; C2864  
};  
  
// Initialize static volatile, non-const, or non-integral  
// data members when defined, not when declared:  
int C::b = 3;  
volatile int C::c = 3;  
volatile const int C::d = 3;  
const double C::f = 3.33;  
```