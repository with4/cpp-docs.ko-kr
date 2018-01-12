---
title: "컴파일러 오류 C2450 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2450
dev_langs: C++
helpviewer_keywords: C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9168071c02140b1a334c1c31acda08edb82b4bec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2450"></a>컴파일러 오류 C2450
'type' 형식의 switch 식은 올바르지 않습니다.  
  
 `switch` 식이 잘못 된 형식으로 계산 합니다. 정수 형식 또는 클래스 형식으로 계산 되어야 정수 형식으로 명확한 변환을 합니다. 사용자 정의 형식으로 계산 되 면 변환 연산자를 제공 해야 합니다.  
  
 다음 샘플에서는 C2450 오류가 생성 됩니다.  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```