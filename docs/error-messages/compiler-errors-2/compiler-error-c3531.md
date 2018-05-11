---
title: 컴파일러 오류 C3531 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69fcacacafba752f77aacd55d5cd57b2c42b5ba9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3531"></a>컴파일러 오류 C3531
'symbol': 'auto'가 포함 된 형식의 기호에는 이니셜라이저가 있어야 합니다.  
  
 지정된 된 변수에 이니셜라이저 식을 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  변수를 선언 하는 경우 등호 구문을 사용 하는 단순 할당과 같은 이니셜라이저 식을 지정 합니다.  
  
## <a name="example"></a>예제  
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