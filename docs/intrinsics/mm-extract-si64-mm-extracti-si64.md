---
title: _mm_extract_si64, _mm_extracti_si64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
dev_langs: C++
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 33467ac3a4397c3f446abe370dca5dc16c1a92ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64
**Microsoft 전용**  
  
 생성 된 `extrq` 하위 64 비트의 첫 번째 인수에서 지정 된 비트를 추출 하는 명령입니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 [in] `Source`  
 입력된 데이터의 하위 64 비트를 128 비트 필드입니다.  
  
 [in]`Descriptor`  
 추출 하는 비트 필드를 설명 하는 128 비트 필드입니다.  
  
 [in]`Length`  
 추출 하는 필드의 길이 지정 하는 정수입니다.  
  
 [in]`Index`  
 추출 하는 필드의 인덱스를 지정 하는 정수  
  
## <a name="return-value"></a>반환 값  
 최하위 비트에서 추출 된 필드와 128 비트 필드입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 이 내장 함수 생성의 `extrq` 의 비트를 추출 하는 명령을 `Source`합니다. 두 가지 버전의이 내장: `_mm_extracti_si64` 은 즉시 버전 및 `_mm_extract_si64` 즉시 라는 것입니다.  각 버전에서 추출 `Source` 비트 필드는 최하위 비트의 인덱스 및 길이 의해 정의 됩니다. 길이 인덱스의 값은 64 mod를-1 및 127 모두 63로 해석 되는 따라서 합니다. (감소) 인덱스와 (감소) 필드 길이 합하면 64 보다 큰 경우 결과가 정의 되지 않습니다. 필드 길이 0 값을 64로 해석 됩니다. 필드 길이 비트 인덱스의 비트 0 개, 두 63:0 경우 `Source` 추출 됩니다. 필드 길이 0 비트 인덱스는 0이 아닌 경우 결과가 정의 되지 않습니다.  
  
 _Mm_extract_si64에 대 한 호출에는 `Descriptor` 13:8 비트 및 비트 5: 0에서 추출할 데이터의 필드 길이 내 인덱스를 포함...  
  
 호출 하는 경우 `_mm_extracti_si64` 컴파일러에서는 XMM 레지스터에 해당 값을 압축 하는 코드 인수는 컴파일러가 정수 상수를 확인할 수 없습니다 (`Descriptor`)를 호출 하 고 `_mm_extract_si64`합니다.  
  
 에 대 한 하드웨어 지원을 확인 하는 `extrq` 명령, 호출의 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 의 6 비트를 확인 하 고 `CPUInfo[2] (ECX)`합니다. 그렇지 않으면이 비트는 명령의 지원 되 면 1과 0 수 있습니다. 지원 하지 않는 내장이 하드웨어를 사용 하는 코드를 실행 하는 경우는 `extrq` 명령 결과 예측할 수 없습니다.  
  
## <a name="example"></a>예제  
  
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
  
```Output  
result1 = 0x30eca86  
result2 = 0x30eca86  
result3 = 0x30eca86  
```  
  
**Microsoft 전용 종료**  
 고급 마이크로 장치, inc 2007 저작권 All rights reserved. 고급 마이크로 장치, Inc. 로부터 사용 권한을 승인 하에 복제  
  
## <a name="see-also"></a>참고 항목  
 [_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)