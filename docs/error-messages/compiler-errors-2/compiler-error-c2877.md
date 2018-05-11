---
title: 컴파일러 오류 C2877 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2877
dev_langs:
- C++
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96ab91d64806e7d4ca28bf43e812640790b78e87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2877"></a>컴파일러 오류 C2877
'symbol'를 'class'에서 액세스할 수 없는 경우  
  
 기본 클래스에서 파생 된 모든 멤버는 파생된 클래스에서 액세스할 수 있어야 합니다.  
  
 다음 샘플에서는 C2877 오류가 생성 됩니다.  
  
```  
// C2877.cpp  
// compile with: /c  
class A {  
private:  
   int a;  
};  
  
class B : public A {  
   using A::a;   // C2877  
};  
```