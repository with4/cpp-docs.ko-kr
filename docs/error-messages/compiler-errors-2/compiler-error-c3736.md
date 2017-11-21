---
title: "컴파일러 오류 C3736 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3736
dev_langs: C++
helpviewer_keywords: C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c2d7f548a1795221a72d0ac7be01e8ed87fa6ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3736"></a>컴파일러 오류 C3736
'event': 메서드여야 또는 관리 되는 이벤트의 경우 데이터 멤버  
  
 기본 모드와 COM 이벤트 메서드여야 합니다. .NET 이벤트 데이터 멤버를 수도 있습니다.  
  
 다음 샘플에서는 C3736 오류가 생성 됩니다.  
  
```  
// C3736.cpp  
struct A {  
   __event int e();  
};  
  
struct B {  
   int f;   // C3736  
   // The following line resolves the error.  
   // int f();  
   B(A* a) {  
      __hook(&A::e, a, &B::f);  
   }  
};  
  
int main() {  
}  
```