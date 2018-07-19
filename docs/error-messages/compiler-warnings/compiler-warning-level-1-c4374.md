---
title: 컴파일러 경고 (수준 1) C4374 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4374
dev_langs:
- C++
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb6304fa921d4b67c5dc33bfa54fbcbb3a722511
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276674"
---
# <a name="compiler-warning-level-1-c4374"></a>컴파일러 경고(수준 1) C4374
'function1': 인터페이스 메서드 'function2' 비가상 메서드에서 구현 하지 것입니다.  
  
 컴파일러를 찾지 못했습니다는 [가상](../../cpp/virtual-specifier.md) 메서드 정의의 키워드입니다.  
  
 다음 샘플에서는 C4374 오류가 생성 됩니다.  
  
```  
// C4374.cpp  
// compile with: /clr /W1 /c /WX  
public interface class I {  
   void f();  
};  
  
public ref struct B {  
   void f() {  
      System::Console::WriteLine("B::f()");  
   }  
};  
  
public ref struct C {  
   virtual void f() {  
      System::Console::WriteLine("C::f()");  
   }  
};  
  
public ref struct D : B, I {};   // C4374  
public ref struct E : C, I {};   // OK  
```