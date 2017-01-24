---
title: "__ll_lshift | Microsoft Docs"
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
  - "__ll_lshift_cpp"
  - "__ll_lshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ll_lshift 내장 함수"
  - "__ll_lshift 내장 함수"
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ll_lshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 지정한 비트 수 만큼 왼쪽으로 이동 하는 제공 된 64 비트 값입니다.  
  
## 구문  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### 매개 변수  
 \[in\] `Mask`  
 왼쪽 시프트 64 비트 정수 값입니다.  
  
 \[in\] `nBit`  
 이동할 비트 수가 있습니다.  
  
## 반환 값  
 마스크 왼쪽으로 시프트 `nBit` 비트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__ll_lshift`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 64 비트 아키텍처를 사용 하 여 프로그램을 컴파일할 경우 및 `nBit` , 63 보다 크고 이동할 비트 수입니다 `nBit` 모듈러스 64.  32 비트 아키텍처를 사용 하 여 프로그램을 컴파일할 경우 및 `nBit` 31 보다 큰 이동할 비트 수가 `nBit` 모듈로 32.  
  
 `ll` 이름에서이 작업에 임을 나타내는 `long long` \(`__int64`\).  
  
## 예제  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## Output  
  
```  
10000  
```  
  
 **참고** 왼쪽된 시프트 연산을 없음 서명 되지 않은 버전입니다.  이 때문에 `__ll_lshift` 이미 서명 되지 않은 입력된 매개 변수를 사용 하 여.  오른쪽 shift 키와는 달리, 없어 없음 기호 종속성에 왼쪽된 시프트, 최하위 비트 결과 항상 이동 값의 부호에 관계 없이 0으로 설정 됩니다.  
  
### Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_ll\_rshift](../intrinsics/ll-rshift.md)   
 [\_\_ull\_rshift](../intrinsics/ull-rshift.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)