---
title: 컴파일러 오류 C3254 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e58976b1562e6cca9aa343401b5d2c3f856de1a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3254"></a>컴파일러 오류 C3254
'명시적 재정의': 클래스 명시적 재정의 'override'를 포함 되어 있지만 함수 선언을 포함 하는 인터페이스에서 파생 되지 않습니다  
  
 때 있습니다 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md) 메서드를 재정의 포함 하는 클래스 파생 되어야, 직접 또는 간접적으로, 재정의 하는 함수가 포함 된 형식에서 합니다.  
  
 다음 샘플에서는 C3254 오류가 생성 됩니다.  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```