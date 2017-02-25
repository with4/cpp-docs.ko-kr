---
title: "_mm_cvttss_si64x | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvttss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_cvttss_si64x 내장 함수"
  - "cvttss2si 명령"
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_cvttss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 X64 확장된 버전 잘라내기 단 정밀도 부동 소수점 숫자를 64 비트 정수를 변환의 방출 \(`cvttss2si`\) 명령.  
  
## 구문  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### 매개 변수  
 \[in\] `value`  
 `__m128` 단 정밀도 부동 소수점 값이 포함 된 구조입니다.  
  
## 반환 값  
 64 비트 정수 처음 부동 소수점 값의 변환의 결과입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_cvttss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장 다릅니다 `_mm_cvtss_si64x` 는 0으로 정확 하지 않습니다 변환만 잘립니다.  때문에 `__m128` 구조는 XMM 레지스터를 나타내는, 생성 된 명령의 데이터는 XMM 레지스터에서 시스템 메모리로 이동 합니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_m128](../cpp/m128.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)