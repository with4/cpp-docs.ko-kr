---
title: "컴파일러 오류 C2602 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2602
dev_langs: C++
helpviewer_keywords: C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bd53ce47aeb31022e042b515409a98b087c6813
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2602"></a>컴파일러 오류 C2602
'class::Identifier' 'class'의 기본 클래스의 구성원이 아닙니다.  
  
 `Identifier`클래스는 기본 클래스에서 상속 된 멤버가 없기 때문에 액세스할 수 없습니다.  
  
 다음 샘플에서는 C2602 오류가 생성 됩니다.  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```