---
title: 컴파일러 오류 C2502 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2502
dev_langs:
- C++
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 093980d1e604eacde92a8ea7aa029f77f57d48b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2502"></a>컴파일러 오류 C2502
'identifier': 기본 클래스에 너무 많은 액세스 한정자  
  
 기본 클래스에 대 한 액세스 한정자가 두 개 이상 있습니다. 하나의 액세스 한정자 (`public`, `private`, 또는 `protected`) ï ´ ù.  
  
 다음 샘플에서는 C2502 오류가 생성 됩니다.  
  
```  
// C2502.cpp  
// compile with: /c  
class A { };  
class B { };  
class C : private public A { };   // C2502  
  
// OK  
class D : private A {};  
class E : public A, private B {};  
```