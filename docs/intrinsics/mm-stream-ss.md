---
title: "_mm_stream_ss | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_stream_ss"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movntss 명령"
  - "_mm_stream_ss 내장 함수"
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_stream_ss
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캐시를 오염 시 키 지 않고 메모리 위치에 32 비트 데이터를 씁니다.  
  
## 구문  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 원본 데이터를 쓰는 위치에 대 한 포인터입니다.  
  
 \[in\] `Source`  
 포함 하는 128 비트 숫자는 `float` 32 비트 바닥에 쓸 값.  
  
## 반환 값  
 없음  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_stream_ss`|SSE4a|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 생성 하는 `movntss` 명령.  이 명령에 대 한 하드웨어 지원을 확인 하려면 호출을 `__cpuid` 와 내장 `InfoType=0x80000001`6 비트를 확인 하 고 `CPUInfo[2] (ECX)`.  명령이 지원되는 경우 비트는 1이고, 그렇지 않으면 0입니다.  
  
 사용 하는 코드를 실행 하는 경우는 `_mm_stream_ss` 에서 지원 하지 않는 하드웨어에 내장의 `movntss` 명령의 결과 없는 예측할 수.  
  
## 예제  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
  
```  
  
  **f \[0\]\-\[1\] f 1 \= \= \[2\]\-2 f\-3, f \[3\] \= \= 3**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [\_mm\_stream\_sd](../intrinsics/mm-stream-sd.md)   
 [\_mm\_stream\_ps](http://msdn.microsoft.com/ko-kr/f7af2f19-c0d4-43c6-b5f6-a658d2b1d869)   
 [\_mm\_store\_ss](http://msdn.microsoft.com/ko-kr/dfeeea35-8faf-4f54-8a9e-6723e226fb08)   
 [\_mm\_sfence](http://msdn.microsoft.com/ko-kr/b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](http://msdn.microsoft.com/ko-kr/8f03493a-d5f5-4457-892e-0b6540494872)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)