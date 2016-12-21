---
title: "_mm_cvtss_si64x | Microsoft Docs"
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
  - "_mm_cvtss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtss2si 내장 함수"
  - "_mm_cvtss_si64x 내장 함수"
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_cvtss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 확장된 버전을 변환 스칼라 단일 정밀도 부동 소수점 숫자로 64 비트 정수 \(`cvtss2si`\) 명령.  
  
## 구문  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### 매개 변수  
 \[in\] `value`  
 `__m128` 부동 소수점 값이 포함 된 구조입니다.  
  
## 반환 값  
 64 비트 정수, 부동 소수점 첫 번째 값의 정수 변환의 결과입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 구조체 값의 첫 번째 요소 정수로 변환 되 고 반환 합니다.  MXCSR 제어 비트 반올림 반올림 동작을 결정 하는 데 사용 됩니다.  기본 반올림 모드는 소수 부분이 0.5 인 경우는 짝수로 반올림 하에서 가장 가까운 라운드입니다.  때문에 `__m128` 구조이 내장 된 XMM 레지스터 XMM 레지스터의 값을 가져와 시스템 메모리에 기록 된 나타냅니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_m128d](../cpp/m128d.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)