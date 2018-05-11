---
title: 컴파일러 오류 C3409 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3409
dev_langs:
- C++
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1964cffd0593e87a790befd8a76ae13847f2058d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3409"></a>컴파일러 오류 C3409
빈 특성 블록을 사용할 수 없습니다.  
  
 대괄호는 컴파일러에 의해 해석 되었습니다는 [특성](../../windows/cpp-attributes-reference.md) 블록 있지만 특성이 없는 찾았습니다.  
  
 람다 식 정의의 일부로 대괄호를 사용 하는 경우 컴파일러에서이 오류를 생성할 수 있습니다. 이 오류는 컴파일러가 대괄호 특성 블록 또는 람다 식 정의의 일부는 지 여부를 확인할 수 없을 때 발생 합니다. 람다 식에 대한 자세한 내용은 [람다 식](../../cpp/lambda-expressions-in-cpp.md)을 참조하세요.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  대괄호 일부인 경우 특성 블록:  
  
    1.  특성 블록에서 하나 이상의 특성을 제공 합니다.  
  
    2.  특성 블록을 제거 합니다.  
  
2.  대괄호는 람다 식의 일부일 경우:  
  
    1.  람다 식 올바른 구문 규칙을 따르는지를 확인 합니다.  
  
         람다 식 구문에 대 한 자세한 내용은 참조 [람다 식 구문](../../cpp/lambda-expression-syntax.md)합니다.  
  
    2.  
  
## <a name="example"></a>예제  
 다음 예제에서는 C3409 오류가 발생 합니다.  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 람다 식을 사용 하 여 C3409 생성은 `mutable` 사양 하지만 매개 변수 목록을 제공 하지 않습니다. 컴파일러는 대괄호 특성 블록 또는 람다 식 정의의 일부는 지 여부를 확인할 수 없습니다.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [특성](../../windows/cpp-attributes-reference.md)   
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)   
 [람다 식 구문](../../cpp/lambda-expression-syntax.md)