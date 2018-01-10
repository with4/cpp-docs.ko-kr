---
title: _ReturnAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReturnAddress
dev_langs: C++
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d207fcba6846d0a5e599d6273f5b35bb554bda40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="returnaddress"></a>_ReturnAddress
## <a name="microsoft-specific"></a>Microsoft 전용  
 `_ReturnAddress` 내장 컨트롤 호출자에 게 반환 된 후 실행 되는 함수 호출에서 명령의 주소를 제공 합니다.  
  
 다음 프로그램 및 단계를 실행 하면 디버거에서 생성 합니다. 프로그램을 통해 실행 함에 따라에서 반환 되는 주소를 기록해 둡니다. `_ReturnAddress`합니다. 다음 함수에서 반환 된 후 즉시 여기서 `_ReturnAddress` 사용 되는, 열기는 [하는 방법: 디스어셈블리 창을 사용 하 여](/visualstudio/debugger/how-to-use-the-disassembly-window) 실행할 다음 명령의 주소 에서반환되는주소와일치하는지확인`_ReturnAddress`.  
  
 인라인 처리 년 5 월 등의 최적화 반송 주소에 영향을 줍니다. 예를 들어 아래 샘플 프로그램은으로 컴파일된 [/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` 호출 함수의 경우에 줄이 그어진 됩니다 `main`합니다. 따라서에 대 한 호출 `_ReturnAddress` 에서 `inline_func` 및 `main` 동일한 값이 각각 생성 됩니다.  
  
 때 `_ReturnAddress` 로 컴파일된 프로그램에서 사용 되는 [/clr](../build/reference/clr-common-language-runtime-compilation.md)를 포함 하는 함수는 `_ReturnAddress` 네이티브 함수 호출 식이 컴파일됩니다. 관리 되는 포함 하는 함수를 호출 하는 함수를 컴파일할 때 `_ReturnAddress`, `_ReturnAddress` 예상 대로 작동 하지 않을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<. h >  
  
## <a name="example"></a>예  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [키워드](../cpp/keywords-cpp.md)