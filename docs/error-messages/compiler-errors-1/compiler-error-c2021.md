---
title: "컴파일러 오류 C2021 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d87775cb88579cae93e4de208b1386ab067a07b8
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
