---
title: "컴파일러 경고 (수준 1) C4750 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 6e22ef89b92a5b584979abbd370f82b482cf74e0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4750"></a>컴파일러 경고(수준 1) C4750
'identifier': 루프에 인라이닝된 _alloca()를 사용하는 함수  
  
 'Identifier' 함수를 인라인 확장을 강제로 [_alloca](../../c-runtime-library/reference/alloca.md) 루프가 실행 되는 경우 스택 오버플로 발생 시킬 수 있는 루프 내에서 함수입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  와 'identifier' 함수를 수정 하지는 [__forceinline](../../cpp/inline-functions-cpp.md) 지정자입니다.  
  
2.  'Identifier' 함수에 포함 되지 않았는지 확인 한 [_alloca](../../c-runtime-library/reference/alloca.md) 루프에 포함 된 함수입니다.  
  
3.  지정 하지 않으면는 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md), 또는 [/Og](../../build/reference/og-global-optimizations.md) 컴파일 스위치입니다.  
  
4.  위치는 [_alloca](../../c-runtime-library/reference/alloca.md) 함수는 [시도-문](../../cpp/try-except-statement.md) 하는 스택 오버플로가 catch 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 루프에서 `MyFunction` 을 호출하고 `MyFunction` 은 `_alloca` 함수를 호출합니다. `__forceinline` 한정자로 인해 `_alloca` 함수의 인라인 확장이 발생합니다.  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [_alloca](../../c-runtime-library/reference/alloca.md)
