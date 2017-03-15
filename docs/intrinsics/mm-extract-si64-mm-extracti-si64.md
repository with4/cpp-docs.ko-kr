---
title: "_mm_extract_si64, _mm_extracti_si64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_extracti_si64"
  - "_mm_extract_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extrq 명령"
  - "_mm_extracti_si64 내장 함수"
  - "_mm_extract_si64 내장 함수"
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_extract_si64, _mm_extracti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `extrq` 의 낮은 64 비트에서 첫 번째 인수를 지정한 비트 압축을 풀려면 명령.  
  
## 구문  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### 매개 변수  
 \[in\]`Source`  
 입력된 데이터의 하위 64 비트와 128 비트 필드입니다.  
  
 \[in\] `Descriptor`  
 추출 하는 비트 필드를 설명 하는 128 비트 필드입니다.  
  
 \[in\] `Length`  
 추출할 필드의 길이 지정 하는 정수입니다.  
  
 \[in\] `Index`  
 추출할 필드의 인덱스를 지정 하는 정수입니다.  
  
## 반환 값  
 해당 lsb에서 추출 된 필드를 사용 하는 128 비트 필드입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 생성 하는 `extrq` 에서 비트 압축을 풀려면 명령 `Source`.두 가지 버전의이 내장: `_mm_extracti_si64` 즉시 버전인 및 `_mm_extract_si64` \-직접 실행 됩니다.  각 버전 추출 `Source` 비트 필드 길이 및 인덱스의 최하위 비트를 정의 합니다.  값의 길이 인덱스가 64 mod 가져옵니다, 그리고 따라서\-1과 127\-63로 해석 됩니다.  \(감소\) 인덱스 및 길이 \(감소\) 필드의 합계 64 보다 큰 경우 결과 정의 되지 않습니다.  필드 길이 대 한 0 값을 64로 해석 됩니다.  필드 길이 비트 인덱스를 모두 0으로 비트 63:0의 경우 `Source` 추출 됩니다.  0이 아닌 비트 인덱스 된 필드 길이가 0 인 경우 결과 정의 되지 않습니다.  
  
 호출에 \_mm\_extract\_si64의 `Descriptor` 13: 8 비트 및 비트 5: 0에서 추출할 데이터 길이 필드의 인덱스를 포함 합니다.  
  
 호출 하는 경우 `_mm_extracti_si64` 컴파일러는 정수 상수 여야 정하지 인수와 함께 컴파일러는 XMM 레지스터를 이러한 값을 압축 하는 코드를 생성 합니다 \(`Descriptor`\)를 호출 하 고 `_mm_extract_si64`.  
  
 하드웨어 지원을 확인 하는 `extrq` 명령, 호출의 `__cpuid` 와 내장 `InfoType=0x80000001` 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`.  이 비트 명령이 지원 되지 않으면 1, 0 그렇지 않으면 됩니다.  내장 지원 하지 않는 하드웨어를 사용 하는 코드를 실행 하는 경우는 `extrq` 명령의 결과 없는 예측할 수 있습니다.  
  
## 예제  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
  **result1 \= 0x30eca86 result2 result3 0x30eca86 \= 0x30eca86 \=**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [\_mm\_insert\_si64, \_mm\_inserti\_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)