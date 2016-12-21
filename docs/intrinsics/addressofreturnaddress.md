---
title: "_AddressOfReturnAddress | Microsoft Docs"
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
  - "_AddressOfReturnAddress_cpp"
  - "_AddressOfReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AddressOfReturnAddress 내장 함수"
  - "AddressOfReturnAddress 내장 함수"
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _AddressOfReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 현재 함수의 반환 주소를 보유 하는 메모리 위치의 주소를 제공 합니다.  이 주소 \(예를 들어, 함수의 인수\) 다른 메모리 위치에 액세스할 수 사용할 수 있습니다.  
  
## 구문  
  
```  
void * _AddressOfReturnAddress();  
```  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_AddressOfReturnAddress`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 때 `_AddressOfReturnAddress` 함께 컴파일되는 프로그램에서 사용 되는  [\/clr](../build/reference/clr-common-language-runtime-compilation.md), 포함 하는 함수는 `_AddressOfReturnAddress` 호출을 네이티브 함수로 컴파일할.  함수는 컴파일할 때 관리 되는 호출을 포함 하는 함수에 `_AddressOfReturnAddress`, `_AddressOfReturnAddress` 예상 대로 작동 하지 않을 수 있습니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// compiler_intrinsics_AddressOfReturnAddress.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
// This function will print three values:  
//   (1) The address retrieved from _AddressOfReturnAdress  
//   (2) The return address stored at the location returned in (1)  
//   (3) The return address retrieved the _ReturnAddress* intrinsic  
// Note that (2) and (3) should be the same address.  
__declspec(noinline)  
void func() {  
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();  
   printf_s("%p\n", pvAddressOfReturnAddress);  
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));  
   printf_s("%p\n", _ReturnAddress());  
}  
  
int main() {  
   func();  
}  
```  
  
  **0012FF78 00401058 00401058**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)