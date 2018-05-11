---
title: 컴파일러 경고 (수준 1) C4358 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4358
dev_langs:
- C++
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f051673f56bfa66d7cd373b6917a9754c5ffd46a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4358"></a>컴파일러 경고(수준 1) C4358
'operator': 반환 결합된 대리자의 형식이 'void'; 반환 되는 값 정의 되지 않습니다.  
  
 두 명의 대리자 결합 되었습니다 및 반환 값은 void 되지 않습니다. Void가 아닌 반환 값이 두 대리자를 결합 하는 경우 컴파일러는 대리자의 반환 값을 사용 하는 경우 적절 한 할당을 수행할 수 있게 됩니다.  
  
 다음 샘플에서는 C4358 오류가 생성 됩니다.  
  
```  
// C4358.cpp  
// compile with: /clr /W1  
delegate int D();  
delegate void E();  
  
ref class X {  
   int i;  
public:  
   X(int ii) : i(ii) {}  
   int f() {  
      return i;  
   }  
};  
  
ref class Y {  
   int i;  
public:  
   Y() {}  
   void g() {}  
};  
  
int main() {  
   D^ d = gcnew D(gcnew X(1), &X::f);  
   D^ d2 = gcnew D(gcnew X(2), &X::f);  
  
   d += d2;   // C4358  
   int j = d();   // return value indeterminate  
  
   E^ e = gcnew E(gcnew Y, &Y::g);  
   E^ e2 = gcnew E(gcnew Y, &Y::g);  
   e += e2;   // OK  
}  
```