---
title: 컴파일러 오류 C2149 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2149
dev_langs:
- C++
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e02d69aa89c77c72685ef0db3125dab2cbf1898b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2149"></a>컴파일러 오류 C2149
'identifier': 명명된 비트 필드의 너비가 0일 수 없습니다.  
  
 비트 필드는 명명되지 않은 경우에만 너비가 0일 수 있습니다.  
  
 다음 샘플에서는 C2149를 생성합니다.  
  
```  
// C2149.cpp  
// compile with: /c  
struct C {  
   int i : 0;   // C2149  
   int j : 2;   // OK  
};  
```