---
title: 컴파일러 오류 C2495 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2495
dev_langs:
- C++
helpviewer_keywords:
- C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be85ad161c719af5dba537a96b2d9c327b06d56e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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