---
title: "_ReturnAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReturnAddress 내장 함수"
  - "ReturnAddress 내장 함수"
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `_ReturnAddress` 내장 명령의 호출자에 게 컨트롤이 반환 된 후에 실행 될 함수 호출에 주소를 제공 합니다.  
  
 다음 프로그램 및 디버거에서 단계를 작성 합니다.  프로그램을 단계별로 실행 하는 것에서 반환 되는 주소를 확인 합니다. `_ReturnAddress`.  함수에서 반환 후 즉시 다음 위치 `_ReturnAddress` 되었습니다 사용 되는, 열려 있는 [방법: 디스어셈블리 창 사용](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md) 다음 명령 실행할 수 있는 주소에서 반환 된 주소와 일치 하는지 확인 합니다. `_ReturnAddress`.  
  
 최적화 인라이닝 월 같은 반송 주소에 영향을 줍니다.  예를 들어, 다음 샘플 프로그램을 컴파일하는 경우  [\/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` 를 호출 하는 함수를 인라인 하지 것입니다 `main`.  따라서 호출을 `_ReturnAddress` 에서 `inline_func` 및 `main` 각각 동일한 값이 생성 됩니다.  
  
 때 `_ReturnAddress` 함께 컴파일되는 프로그램에서 사용 되는  [\/clr](../build/reference/clr-common-language-runtime-compilation.md), 포함 하는 함수는 `_ReturnAddress` 호출을 네이티브 함수로 컴파일할 수.  함수는 컴파일할 때 관리 되는 호출을 포함 하는 함수에 `_ReturnAddress`, `_ReturnAddress` 예상 대로 동작 하지 않을 수 없습니다.  
  
## 요구 사항  
 **헤더 파일** \<intrin.h\>  
  
## 예제  
  
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
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)