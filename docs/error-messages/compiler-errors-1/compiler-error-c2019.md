---
title: 컴파일러 오류 C2019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2019
dev_langs:
- C++
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8f9f36bef278edc4c40c732b86c012180535f74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164243"
---
# <a name="compiler-error-c2019"></a>컴파일러 오류 C2019
전처리기 지시문이 있어야 하는데 'character'가 있습니다.  
  
 다음에 오는 문자는 `#` 부호는 전처리기 지시문의 첫 번째 문자가 아닙니다.  
  
 다음 샘플에서는 C2019 오류가 생성 됩니다.  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 해결 방법:  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```