---
title: "컴파일러 오류 C2650 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c3352820434c8d794d4980a606cb945bd8ecc4a8
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
