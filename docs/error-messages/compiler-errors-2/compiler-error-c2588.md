---
title: 컴파일러 오류 C2588 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67eb6362ff55e09b05349d10fcdc2377d8ff2996
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2588"></a>컴파일러 오류 C2588
':: ~ identifier': 잘못 된 글로벌 소멸자  
  
 소멸자는 클래스, 구조체 또는 공용 구조체 이외의 용도로 정의 됩니다. 이것은 허용되지 않습니다.  
  
 이 오류는 누락 된 클래스, 구조체 또는 공용 구조체 이름은 범위 결정의 왼쪽에 의해 발생할 수 있습니다 (`::`) 연산자.  
  
 다음 샘플에서는 C2588 오류가 생성 됩니다.  
  
```  
// C2588.cpp  
~F();   // C2588  
```