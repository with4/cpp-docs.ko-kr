---
title: "컴파일러 경고 (수준 1) C4374 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4374
dev_langs: C++
helpviewer_keywords: C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9beaf582360c9e2dab6c40a32db937d3027a9d42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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