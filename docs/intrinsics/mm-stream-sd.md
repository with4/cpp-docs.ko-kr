---
title: "_mm_stream_sd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_stream_sd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_stream_sd 내장 함수"
  - "movntsd 명령"
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_stream_sd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 64 비트 데이터는 캐시를 오염 시 키 지 않고 메모리 위치에 씁니다.  
  
## 구문  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### 매개 변수  
 \[out\]`Dest`  
 원본 데이터를 기록할 위치에 대 한 포인터입니다.  
  
 \[in\] `Source`  
 128 비트 값을 포함 하는 `double` 64 비트 바닥에 쓸 값.  
  
## 반환 값  
 없음  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_stream_sd`|SSE4a|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 생성 하는 `movntsd` 명령.  이 명령에 대 한 하드웨어 지원을 확인 하려면 호출을 `__cpuid` 와 내장 `InfoType=0x80000001` 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`.  하드웨어가 명령과 0 지 그렇지 않으면 원하는 경우이 비트는 1입니다.  
  
 사용 하는 코드를 실행 하는 경우는 `_mm_stream_sd` 에서 지원 하지 않는 하드웨어에 내장의 `movntsd` 명령의 결과 없는 예측할 수.  
  
## 예제  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
  **d \[0\]\-1 d \[1\] \= \= 1**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [\_mm\_stream\_ss](../intrinsics/mm-stream-ss.md)   
 [\_mm\_store\_sd](http://msdn.microsoft.com/ko-kr/8e672d0d-0a96-45b9-a783-392a2457de42)   
 [\_mm\_sfence](http://msdn.microsoft.com/ko-kr/b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](http://msdn.microsoft.com/ko-kr/8f03493a-d5f5-4457-892e-0b6540494872)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)