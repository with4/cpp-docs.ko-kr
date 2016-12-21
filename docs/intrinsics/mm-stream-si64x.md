---
title: "_mm_stream_si64x | Microsoft Docs"
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
  - "_mm_stream_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movnti 명령"
  - "_mm_stream_si64x 내장 함수"
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_stream_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 MOVNTI 명령을 생성합니다.  데이터 기록 `Source` 에 의해 지정 된 메모리 위치 `Dest`, 캐시를 오염 시 키 지 않고.  
  
## 구문  
  
```  
void _mm_stream_si64x(   
   __int64 * Dest,   
   __int64 Source   
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 원본 데이터를 쓸 위치에 대 한 포인터입니다.  
  
 \[in\] `Source`  
 쓸 데이터입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_mm_stream_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// _mm_stream_si64x.c  
// processor: x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_mm_stream_si64x)  
  
int main()  
{  
    __int64 val = 0xFFFFFFFFFFFFI64;  
    __int64 a[10];  
  
    memset(a, 0, sizeof(a));  
    _mm_stream_si64x(a+1, val);  
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
  **0 0 0 ffffffffffff**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [Cache Support for Streaming SIMD Extensions 2 Integer Operations](http://msdn.microsoft.com/ko-kr/a9c9b42f-de9e-4374-aeb6-5f65bfb669b6)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)