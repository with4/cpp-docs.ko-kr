---
title: 컴파일러 오류 C2783 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2783
dev_langs:
- C++
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c16e74e8187b92778eda3392560d2f9a02e05b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234405"
---
# <a name="compiler-error-c2783"></a>컴파일러 오류 C2783
'declaration': 'identifier'에 대 한 템플릿 인수를 추론할 수 없습니다  
  
 컴파일러는 템플릿 인수를 확인할 수 없습니다. 기본 인수는 템플릿 인수 추론을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2783 오류가 생성 됩니다.  
  
```  
// C2783.cpp  
template<typename T1, typename T2>  
T1 f(T2) {  
   return 248;  
}  
  
int main() {  
   f(1);   // C2783  
   // try the following line instead  
   int i = f<int>(1);  
}  
```  
  
 C2783은 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C2783b.cpp  
// compile with: /clr  
using namespace System;  
generic<typename T1, typename T2>   
T1 gf(T2) {  
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));  
   return t1;  
}  
  
ref class MyClass{};  
  
int main() {  
   int i;  
   i = gf(9);   // C2783  
  
   // OK  
   i = gf<int>(9);  
}  
```