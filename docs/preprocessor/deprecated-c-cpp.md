---
title: (C/c + +) 사용 되지 않습니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
dev_langs:
- C++
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2280d5245292625bfc29815475eaca63d4d500bd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="deprecated-cc"></a>사용되지 않음 (C/C++)
**사용 되지 않는** pragma는 함수, 형식 또는 다른 식별자 더 이상 지원 되지 않을 이후에서 표시를 사용 하면 임대 해제 또는 더 이상 사용 해야 합니다.  
> [!NOTE]
> C + + 14에 대 한 내용은 `[[deprecated]]` Microsoft declspec 또는 pragma vs 특성, 참조 특성을 포함 하며 해당 복사본을 사용 하는 시기에 대 한 지침 [c + + 표준 특성](../cpp/attributes.md) 특성입니다.
  
## <a name="syntax"></a>구문  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>설명  
 컴파일러는 식별자가 지정 하 여 발생 했을 때는 **사용 되지 않는** pragma를 사용 하면 컴파일러 경고 발급 [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)합니다.   
  
 매크로 이름을 사용하지 않을 수 있습니다. 매크로 이름을 따옴표로 묶지 않으면 매크로 확장이 발생합니다.  
  
 때문에 **사용 되지 않는** , 특정 버전의 오버 로드 된 함수를 사용 되지 않도록 지정 하는 가장 좋은 방법은 없는 pragma 모든 일치 하는 식별자에서 작동 하며 서명을에 고려 되지 않습니다. 범위에가 일치 하는 함수 이름이 모두 경고를 트리거합니다.

  C + + 14를 사용 하는 것이 좋습니다 `[[deprecated]]` 특성 대신 가능 하면는 **사용 되지 않는** pragma입니다. Microsoft 전용 [__declspec (deprecated)](../cpp/deprecated-cpp.md) 선언 한정자도 하는 것이 보다 많은 경우에는 **사용 되지 않는** pragma입니다. `[[deprecated]]` 특성 및 `__declspec(deprecated)` 한정자를 사용 하면 특정 형태의 오버 로드 된 함수에 대 한 사용 되지 않는 상태를 지정할 수 있습니다. 진단 경고에만 표시 하는 특정 오버 로드 된 함수에 대 한 참조 특성 또는 한정자에 적용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 다음 샘플에서는 클래스를 사용하지 않는 방법을 보여 줍니다.  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)