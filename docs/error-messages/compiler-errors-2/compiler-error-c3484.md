---
title: 컴파일러 오류 C3484 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3484
dev_langs:
- C++
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de302987e4ea56e9ee6f29bed1b5842579a8f5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3484"></a>컴파일러 오류 C3484
반환 형식 앞에 '->'가 필요합니다.  
  
 람다 식의 반환 형식 앞에 `->` 를 제공해야 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   반환 형식 앞에 `->` 를 제공합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 C3484를 생성합니다.  
  
```  
// C3484a.cpp  
  
int main()  
{  
   return []() . int { return 42; }(); // C3484  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 람다 식의 반환 형식 앞에 `->` 를 제공하여 C3484를 해결합니다.  
  
```  
// C3484b.cpp  
  
int main()  
{  
   return []() -> int { return 42; }();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)