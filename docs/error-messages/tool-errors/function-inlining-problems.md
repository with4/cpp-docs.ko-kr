---
title: 함수 인라이닝 문제 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97ffa56fc748eea8f65f5fe79c7a9defa7238f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="function-inlining-problems"></a>함수 인라이닝 문제
함수 인라이닝를 사용 하는 경우 다음을 수행 해야 합니다.  
  
-   포함 하는 헤더 파일에서 구현 된 인라인 함수를 가집니다.  
  
-   가 인라인 처리 헤더 파일에서 ON으로 설정 합니다.  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 그리고  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 사용 하는 경우는 `#pragma inline_depth` 설정 2 이상 값이 있는 컴파일러 지시문을 있는지 확인 하십시오. 값 0은 해제 인라인 처리 합니다. 또한 사용 하 고 있는지를 확인는 **/Ob1** 또는 **/Ob2** 컴파일러 옵션입니다.  
  
 서로 다른 모듈에서 인라인 및 인라인이 아닌 컴파일 옵션을 혼합 하면 문제가 발생할 수 있습니다. C + + 라이브러리 함수 인라이닝 설정 만들어집니다 ([/Ob1](../../build/reference/ob-inline-function-expansion.md) 또는 [/Ob2](../../build/reference/ob-inline-function-expansion.md)) 함수를 설명 하는 해당 헤더 파일에 인라이닝 (옵션 없음)을 해제 하지만, LNK2001 오류가 발생 합니다. 함수 인라인되지 코드에는 헤더 파일에서 하지만 없기 때문에 라이브러리 파일에 없는 주소가 참조를 확인할 수 없습니다.  
  
 마찬가지로, 인라인 함수를 사용 하는 프로젝트 함수를 정의.cpp 파일에서 헤더에서 파일 대신은 또한 LNK2019 합니다. 헤더 파일 포함 everywhere, 적절 한 것으로 간주 되지만 기능은 인라인.cpp 파일 컴파일러 통해 전달 될 때 따라서 링커가 외부 다른 모듈에서 사용 될 때 확인 되지 않은 참조로 함수를 볼 수 있습니다.  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 그런 다음  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 그런 다음  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)