---
title: "_mm_cvtsi64x_ss | Microsoft Docs"
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
  - "_mm_cvtsi64x_ss"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtsi2ss 명령"
  - "_mm_cvtsi64x_ss 내장 함수"
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_cvtsi64x_ss
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 스칼라 단 정밀도 부동 소수점 값으로 변환 하는 64 비트 정수의 확장된 버전 \(`cvtsi2ss`\) 명령.  
  
## 구문  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### 매개 변수  
 \[in\] `a`  
 `__m128` 4 단 정밀도 부동 소수점 값이 포함 된 구조입니다.  
  
 \[in\] `b`  
 부동 소수점 값으로 변환할 수 있는 64 비트 정수입니다.  
  
## 반환 값  
 `__m128` 구조 첫 부동 소수점 값의 변환 결과입니다.  세 값에서 변경 되지 않은 상태로 복사 됩니다 `a`.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_cvtsi64x_ss`|x64|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `__m128` 구조는 XMM 레지스터를 나타내는, 따라서이 내장 값 허용 `b` 등록 시스템 메모리는 XMM로 이동할 수 있습니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// _mm_cvtsi64x_ss.cpp  
// processor: x64  
  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtsi64x_ss)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    a.m128_f32[0] = 0;  
    a.m128_f32[1] = 0;  
    a.m128_f32[2] = 0;  
    a.m128_f32[3] = 0;  
    a = _mm_cvtsi64x_ss(a, b);  
  
    printf_s( "%lf %lf %lf %lf\n",  
              a.m128_f32[0], a.m128_f32[1],   
              a.m128_f32[2], a.m128_f32[3] );  
}  
```  
  
  **54.000000 0.000000 0.000000 0.000000**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_m128](../cpp/m128.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)