---
title: "__ll_rshift | Microsoft Docs"
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
  - "__ll_rshift_cpp"
  - "__ll_rshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ll_rshift 내장 함수"
  - "ll_rshift 내장 함수"
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ll_rshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 두 번째 매개 변수에 의해 지정 된 비트 수 오른쪽 첫 번째 매개 변수에 의해 지정 된 64 비트 값을 이동 합니다.  
  
## 구문  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### 매개 변수  
 \[in\] `Mask`  
 오른쪽으로 이동 하는 64 비트 정수 값입니다.  
  
 \[in\] `nBit`  
 이동할 64 x 64의 나머지와 나머지 x 86 32 비트 개수입니다.  
  
## 반환 값  
 마스크를 이동 하 여 `nBit` 비트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__ll_rshift`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 두 번째 매개 변수 \(32\) x 86에서 x 64에서 64 보다 크면 해당 번호 모듈러스 64 \(32 x 86\) 이동할 비트 수를 확인 하지 않습니다.  `ll` 접두사가 작업에서 임을 나타냅니다 `long long`, 다른 이름 `__int64`, 64 비트 부호 있는 정수 계열 형식입니다.  
  
## 예제  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## Output  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **참고** 경우 `_ull_rshift` 되었습니다 원하는 결과가 음수 값의 경우 가져온 것 없습니다 있도록 사용 하면 MSB 오른쪽 이동 값을 0, 했을 것입니다.  
  
### Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_ll\_lshift](../intrinsics/ll-lshift.md)   
 [\_\_ull\_rshift](../intrinsics/ull-rshift.md)