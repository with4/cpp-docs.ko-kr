---
title: "컴파일러 경고 (수준 1) C4805 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4805
dev_langs:
- C++
helpviewer_keywords:
- C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01e16abcd1a0b94cde1f3491ca519f85982f1ecb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4805"></a>컴파일러 경고(수준 1) C4805
'operation': 연산에 'type' 형식과 'type' 형식을 함께 사용하는 것은 안전하지 않습니다.  
  
 이 경고는 [bool](../../cpp/bool-cpp.md) 과 [int](../../c-language/integer-types.md)간의 비교 작업에 대해 생성됩니다. 다음 샘플에서는 C4805를 생성합니다.  
  
```  
// C4805.cpp  
// compile with: /W1  
int main() {  
   int i = 1;  
   bool b = true;  
  
   if (i == b) {   // C4805, comparing bool and int variables  
   }  
}  
```