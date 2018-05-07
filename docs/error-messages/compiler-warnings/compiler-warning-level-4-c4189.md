---
title: 컴파일러 경고 (수준 4) C4189 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4189
dev_langs:
- C++
helpviewer_keywords:
- C4189
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f15efc139f9f09b86f77569349065719bace677
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4189"></a>컴파일러 경고(수준 4) C4189
'identifier': 지역 변수가 초기화되었으나 참조되지 않았습니다.  
  
 변수가 선언 및 초기화되었지만 사용되지 않습니다.  
  
 다음 샘플에서는 C4189를 생성합니다.  
  
```  
// C4189.cpp  
// compile with: /W4  
int main() {  
   int a = 1;   // C4189, remove declaration to resolve  
}  
```