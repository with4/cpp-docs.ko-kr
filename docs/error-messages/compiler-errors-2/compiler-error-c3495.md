---
title: 컴파일러 오류 C3495 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7accbc422256abbd75d518acce72c522fbb67c14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253664"
---
# <a name="compiler-error-c3495"></a>컴파일러 오류 C3495
'var': 람다 캡처에는 자동 저장 기간이 있어야 합니다.  
  
 `static` 또는 `extern`으로 표시된 변수와 같이 자동 저장 기간이 없는 변수를 캡처할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   람다 식의 캡처 목록에 `static` 또는 `extern` 변수를 전달하지 마세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `static` 변수 `n` 이 람다 식의 캡처 목록에 나타나므로 C3495를 생성합니다.  
  
```  
// C3495.cpp  
  
int main()  
{  
   static int n = 66;  
   [&n]() { return n; }(); // C3495  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)   


