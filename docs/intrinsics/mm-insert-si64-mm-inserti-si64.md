---
title: "_mm_insert_si64, _mm_inserti_si64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_inserti_si64"
  - "_mm_insert_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insertq 명령"
  - "_mm_insert_si64 내장 함수"
  - "_mm_inserti_si64 내장 함수"
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_insert_si64, _mm_inserti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `insertq` 명령 피연산자에서 둘째 피연산자는 첫째 피연산자에 비트를 삽입 합니다.  
  
## 구문  
  
```  
__m128i _mm_insert_si64(  
   __m128i Source1,  
   __m128i Source2  
);  
__m128i _mm_inserti_si64(  
   __m128i Source1,  
   __m128i Source2  
   int Length,  
   int Index  
);  
```  
  
#### 매개 변수  
 \[in\]`Source1`  
 데이터 입력된 필드 삽입 될 하위 64 비트와 128 비트 필드입니다.  
  
 \[in\] `Source2`  
 해당 하위 비트에 삽입할 데이터를 128\-비트 필드입니다.  에 대 한 `_mm_insert_si64`, 또한 한 필드 설명자에는 상위 비트가 포함 되어 있습니다.  
  
 \[in\] `Length`  
 삽입할 필드의 길이 지정 하는 정수 상수입니다.  
  
 \[in\] `Index`  
 인덱스의 최하위 비트 필드에 데이터를 삽입할 지정 하는 정수 상수입니다.  
  
## 반환 값  
 128\-비트 필드의 하위 64 비트 포함의 원래 하위 64 비트 `Source1` 필드에 지정 된 비트의 낮은 비트를 대체 `Source2`.  반환 값의 상위 64 비트는 정의 되지 않습니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 생성 하는 `insertq` 에서 비트를 삽입 하려면 명령 `Source2` 에 `Source1`.  두 가지 버전의이 내장: `_mm_inserti_si64`, 즉시 버전인 및 `_mm_insert_si64` \-직접 실행 됩니다.  각 버전 비트 필드의 길이가 지정 된 원본에서 추출 하 고 source1에 삽입 합니다.  추출 된 비트 lsb 원본입니다.  이러한 비트 삽입 되는 필드 Source1 길이 인덱스의 최하위 비트를 통해 정의 됩니다.  값의 길이 인덱스가 64 mod 가져옵니다, 그리고 따라서\-1과 127\-63로 해석 됩니다.  \(감소\) 비트의 인덱스 및 길이 \(감소\) 필드의 합계 64 보다 큰 경우 결과 정의 되지 않습니다.  필드 길이 대 한 0 값을 64로 해석 됩니다.  필드 길이 비트 인덱스를 모두 0으로 비트 63:0의 경우 `Source2` 삽입 되므로 `Source1`.  0이 아닌 비트 인덱스 된 필드 길이가 0 인 경우 결과 정의 되지 않습니다.  
  
 \_Mm\_insert\_si64를 호출할 비트 77:72 원본 및 색인에 69:64 비트 필드 길이가 포함 되어 있습니다.  
  
 호출 하는 경우 `_mm_inserti_si64`컴파일러는 정수 상수 여야 정하지 인수와 함께 컴파일러는 XMM 레지스터를 이러한 값을 압축 하 고 호출 하는 코드를 생성 합니다. `_mm_insert_si64`.  
  
 에 대 한 하드웨어 지원을 확인 하는 `insertq` 명령 호출을 `__cpuid` 내장 형식으로 `InfoType=0x80000001` 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`.  이 비트 명령이 지원 되지 않으면 1, 0 그렇지 않으면 됩니다.  코드를 사용 하 여 내장이 지원 하지 않는 하드웨어에서 실행 하 여 경우는 `insertq` 명령의 결과 없는 예측 합니다.  
  
## 예제  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source1, source2, source3, result1, result2, result3;  
  
int  
main()  
{  
  
    __int64 mask;  
  
    source1.ui64[0] = 0xffffffffffffffffll;  
    source2.ui64[0] = 0xfedcba9876543210ll;  
    source2.ui64[1] = 0xc10;  
    source3.ui64[0] = source2.ui64[0];  
  
    result1.m = _mm_insert_si64 (source1.m, source2.m);  
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);  
    mask = 0xffff << 12;  
    mask = ~mask;  
    result3.ui64[0] = (source1.ui64[0] & mask) |  
                      ((source2.ui64[0] & 0xffff) << 12);  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
  
}  
```  
  
  **result1 \= 0xfffffffff3210fff result2 result3 0xfffffffff3210fff \= 0xfffffffff3210fff \=**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [\_mm\_extract\_si64, \_mm\_extracti\_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)