---
title: __noop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __noop_cpp
- __noop
dev_langs:
- C++
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ed6228d145261edc323ca0f90899e42dcf02f46
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="noop"></a>__noop
**Microsoft 전용**  
  
 `__noop` 내장 함수를 무시 해야 함을 지정 하 고 인수 목록을 구문 분석할 수 있지만 코드가 생성 되지 인수입니다. 가변 개수의 인수를 사용 하는 전역 디버그 함수에서 사용 하기 위해 두는 것이 됩니다.  
  
 컴파일러는 변환 된 `__noop` 내장 함수를 컴파일 타임에는 0입니다.  
  
## <a name="example"></a>예  
 다음 코드는 사용 하는 방법을 보여 줍니다. `__noop`합니다.  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [키워드](../cpp/keywords-cpp.md)