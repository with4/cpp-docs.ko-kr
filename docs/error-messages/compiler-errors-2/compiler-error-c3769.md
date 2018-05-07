---
title: 컴파일러 오류 C3769 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5258c3dadd7ede384520b76e95c1b8e691882f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3769"></a>컴파일러 오류 C3769
'type': 중첩 된 클래스에는 바로 바깥쪽 클래스와 동일한 이름을 가질 수 없습니다  
  
 중첩된 클래스 바로 바깥쪽의 클래스와 같은 이름을 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3769 오류가 발생 합니다.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```