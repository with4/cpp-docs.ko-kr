---
title: 컴파일러 오류 C3085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3085
dev_langs:
- C++
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57c85908d808243be8e6edce27ea22c18b4941f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3085"></a>컴파일러 오류 C3085
'constructor': 생성자는 'keyword'일 수 없습니다.  
  
 생성자가 잘못 선언되었습니다. 자세한 내용은 [Override Specifiers](../../windows/override-specifiers-cpp-component-extensions.md) 를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3085를 생성합니다.  
  
```  
// C3085.cpp  
// compile with: /c /clr  
ref struct S {  
   S() abstract;   // C3085  
   S(S%) abstract;   // C3085  
};  
  
ref struct T {  
   T() sealed {}   // C3085  
   T(T%) sealed {}   // C3085  
};  
```