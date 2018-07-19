---
title: 컴파일러 오류 C2021 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae1c3640b4fbe5b1473c2e678406321f5533e586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167504"
---
# <a name="compiler-error-c2021"></a>컴파일러 오류 C2021
'character'가 아니라 지수 값이 필요합니다.  
  
 부동 소수점 상수의 지 수로 사용 되는 문자는 유효한 숫자가 아닙니다. 범위에 있는 지 수를 사용 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2021 오류가 생성 됩니다.  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## <a name="example"></a>예제  
 해결 방법:  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```