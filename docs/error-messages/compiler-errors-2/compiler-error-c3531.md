---
title: "컴파일러 오류 C3531 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7c8158d798df3fb48c45194ff6a01a1cbf3ab4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3531"></a>컴파일러 오류 C3531
'symbol': 'auto'가 포함 된 형식의 기호에는 이니셜라이저가 있어야 합니다.  
  
 지정된 된 변수에 이니셜라이저 식을 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  변수를 선언 하는 경우 등호 구문을 사용 하는 단순 할당과 같은 이니셜라이저 식을 지정 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 때문에 c 3531 변수 `x1`, `y1, y2, y3`, 및 `z2` 요소가 초기화 되지 않았습니다.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)