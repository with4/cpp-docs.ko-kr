---
title: 컴파일러 오류 C2344 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2344
dev_langs:
- C++
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdbe2ac9c1533a22e5e77f1d3f2db5c73ef93a3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222165"
---
# <a name="compiler-error-c2344"></a>컴파일러 오류 C2344
align(#): 맞춤은 2의 거듭제곱이어야 합니다.  
  
 [align](../../cpp/align-cpp.md) 키워드를 사용하는 경우 전달하는 값이 2의 거듭제곱이어야 합니다.  
  
 예를 들어 3은 2의 거듭제곱이 아니므로 다음 코드는 C2344를 생성합니다.  
  
```  
// C2344.cpp  
// compile with: /c  
__declspec(align(3)) int a;   // C2344  
__declspec(align(4)) int b;   // OK  
```