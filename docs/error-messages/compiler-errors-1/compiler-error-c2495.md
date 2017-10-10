---
title: "컴파일러 오류 C2495 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2495
dev_langs:
- C++
helpviewer_keywords:
- C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7daef885e27c30a78f7eb02f2573f700146af6ff
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2495"></a>컴파일러 오류 C2495
'identifier': 'nothrow' 함수 선언 또는 정의에 적용 될 수 있습니다  
  
 [nothrow](../../cpp/nothrow-cpp.md) 함수 선언 또는 정의에 확장된 특성을 적용할 수 있습니다.  
  
 다음 샘플에서는 C2495 오류가 생성 됩니다.  
  
```  
// C2495.cpp  
// compile with: /c  
__declspec(nothrow) class X {   // C2495  
   int m_data;  
} x;  
  
__declspec(nothrow) void test();   // OK  
```
