---
title: "_bittestandreset, _bittestandreset64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_bittestandreset64_cpp"
  - "_bittestandreset"
  - "_bittestandreset_cpp"
  - "_bittestandreset64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bittestandreset 내장"
  - "_bittestandreset64 내장"
  - "btr 명령"
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _bittestandreset, _bittestandreset64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 주소 `a`의 비트 `b`를 검사하고 현재 값을 반환한 다음 비트를 0으로 다시 설정하는 명령을 생성합니다.  
  
## 구문  
  
```  
unsigned char _bittestandreset(    long *a,    long b ); unsigned char _bittestandreset64(    __int64 *a,    __int64 b );  
```  
  
#### 매개 변수  
 \[in, out\] `a`  
 검사할 메모리에 대한 포인터입니다.  
  
 \[in\] `b`  
 테스트할 비트 위치입니다.  
  
## 반환 값  
 지정한 위치에 있는 비트입니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_bittestandreset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandreset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
## 예제  
  
```  
// bittestandreset.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <limits.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandreset)  
  
// Check the sign bit and reset to 0 (taking the absolute value)  
// Returns 0 if the number is positive or zero  
// Returns 1 if the number is negative  
unsigned char absolute_value(long* p)  
{  
   const int SIGN_BIT = 31;  
   return _bittestandreset(p, SIGN_BIT);  
}  
  
int main()  
{  
    long i = -112;  
    unsigned char result;  
  
    // Check the sign bit and reset to 0 (taking the absolute value)  
  
    result = absolute_value(&i);  
    if (result == 1)  
        printf_s("The number was negative.\n");     
}  
```  
  
  **숫자가 음수입니다.**   
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)