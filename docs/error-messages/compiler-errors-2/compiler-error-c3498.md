---
title: "컴파일러 오류 C3498 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3498
dev_langs: C++
helpviewer_keywords: C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d895c0dc40d94d6a8fcd567173e2d596e68e333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3498"></a>컴파일러 오류 C3498
'var': 관리 되는 변수 또는 WinRTtype 캡처할 수 없습니다  
  
 람다에 관리되는 형식 또는 Windows 런타임 형식이 있는 변수를 캡처할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   관리되는 또는 Windows 런타임 변수를 람다 식의 매개 변수 목록에 전달합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 관리되는 형식이 있는 변수가 람다 식의 캡처 목록에 나타나므로 C3498을 생성합니다.  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 관리되는 변수`s`를 람다 식의 매개 변수 목록에 전달하여 C3498을 해결합니다.  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)