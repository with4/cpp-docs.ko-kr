---
title: "컴파일러 오류 C2078 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2078
dev_langs:
- C++
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0547cac2c5468558f67aa52a1d59ec9589de86b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2078"></a>컴파일러 오류 C2078
이니셜라이저가 너무 많습니다.  
  
 이니셜라이저 수가 초기화할 개체 수를 초과합니다.  
  
 이니셜라이저 목록에서 내부 중괄호를 생략하면 컴파일러가 개체 및 내부 개체에 대한 올바른 이니셜라이저 할당을 추론할 수 있습니다. 또한 완전한 중괄호를 사용하면 모호성이 제거되고 올바르게 할당됩니다. 부분 중괄호를 사용하면 개체에 대한 이니셜라이저 할당의 모호성으로 인해 C2078 오류가 발생할 수 있습니다.  
  
 다음 샘플에서는 C2078 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2078.cpp  
// Compile by using: cl /c /W4 C2078.cpp  
struct S {  
   struct {  
      int x, y;  
   } z[2];  
};  
  
int main() {  
   int d[2] = {1, 2, 3};   // C2078  
   int e[2] = {1, 2};      // OK  
  
   char a[] = {"a", "b"};  // C2078  
   char *b[] = {"a", "b"}; // OK  
   char c[] = {'a', 'b'};  // OK  
  
   S s1{1, 2, 3, 4};       // OK  
   S s2{{1, 2}, {3, 4}};   // C2078  
   S s3{{1, 2, 3, 4}};     // OK  
   S s4{{{1, 2}, {3, 4}}}; // OK  
}  
  
```