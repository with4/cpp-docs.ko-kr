---
title: 컴파일러 오류 C2650 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee76b2d80ff76033f6776b91ee90e52ef5e200cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2650"></a>컴파일러 오류 C2650
'operator': 가상 함수 일 수 없습니다  
  
 A `new` 또는 `delete` 연산자가 선언 `virtual`합니다. 이러한 연산자는 `static` 멤버 함수 및 커야 `virtual`합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2650 오류가 생성 됩니다.  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```