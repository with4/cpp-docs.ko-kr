---
title: 컴파일러 오류 C2807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2807
dev_langs:
- C++
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 538cdfe6ce8c199a213077e26c16fce65e55b9b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237018"
---
# <a name="compiler-error-c2807"></a>컴파일러 오류 C2807
'operator 연산자' 후 위 두 번째 형식 매개 변수 'int' 여야 합니다.  
  
 후 위 연산자는 두 번째 매개 변수 형식이 잘못 되었습니다.  
  
 다음 샘플에서는 C2807 오류가 생성 됩니다.  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```