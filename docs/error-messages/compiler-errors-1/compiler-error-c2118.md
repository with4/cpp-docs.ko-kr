---
title: 컴파일러 오류 C2118 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2118
dev_langs:
- C++
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c27b4b253e2696b88763c2a9f99c0476f9c46dd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2118"></a>컴파일러 오류 C2118
음수 아래 첨자  
  
 배열 크기를 정의 값이 최대 배열 크기 보다 큰 또는 0 보다 작습니다.  
  
 다음 샘플에서는 C2118 오류가 생성 됩니다.  
  
```  
// C2118.cpp  
int main() {  
   int array1[-1];   // C2118  
   int array2[3];   // OK  
}  
```