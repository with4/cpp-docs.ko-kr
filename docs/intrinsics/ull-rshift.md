---
title: "__ull_rshift | Microsoft Docs"
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
  - "__ull_rshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ull_rshift 내장 함수"
  - "__ull_rshift 내장 함수"
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ull_rshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 x 64에서 두 번째 매개 변수에 의해 지정 된 비트 수 오른쪽 첫 번째 매개 변수에 의해 지정 된 64 비트 값 이동.  
  
## 구문  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### 매개 변수  
 \[in\] `mask`  
 오른쪽으로 이동 하는 64 비트 정수 값입니다.  
  
 \[in\] `nBit`  
 나머지 x 86 32 및 64 x 64에서 모듈로 이동할 비트 수가 있습니다.  
  
## 반환 값  
 마스크를 이동 하 여 `nBit` 비트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__ull_rshift`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 두 번째 매개 변수 \(63\) x 64에서 x 86 31 보다 큰 경우, 해당 번호 모듈러스 \(64 x 64에서\) 32 이동할 비트 수를 확인 하지 않습니다.  `ull` 의 이름을 나타내는 `unsigned long long (unsigned __int64)`.  
  
## 예제  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## Output  
  
```  
1  
```  
  
### Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_ll\_lshift](../intrinsics/ll-lshift.md)   
 [\_\_ll\_rshift](../intrinsics/ll-rshift.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)