---
title: "컴파일러 오류 C3487 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 566f130e3d65826feecc02afae0cc1a7db335efe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3487"></a>컴파일러 오류 C3487
'return type': 모든 반환 식은 같은 형식에 추론되어야 합니다. 이전에는 'return type'이었습니다.  
  
 람다는 단일 return 문을 포함하지 않는 경우 해당 반환 형식을 지정해야 합니다. 람다에 여러 개의 return 문이 포함된 경우 모두 동일한 형식이어야 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   람다에 후행 반환 형식을 지정합니다. 람다의 모든 반환 값이 동일한 형식이거나 반환 형식으로 암시적으로 변환할 수 있는지 확인합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 람다의 반환 형식이 일치하지 않으므로 C3487을 생성합니다.  
  
```  
// C3487.cpp  
// Compile by using: cl /c /W4 C3487.cpp  
  
int* test(int* pi) {  
   // To fix the error, uncomment the trailing return type below  
   auto odd_pointer = [=]() /* -> int* */ {  
      if (*pi % 2)   
         return pi;  
      return nullptr; // C3487 - nullptr is not an int* type  
   };  
   return odd_pointer();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)