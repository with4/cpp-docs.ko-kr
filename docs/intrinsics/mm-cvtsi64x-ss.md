---
title: _mm_cvtsi64x_ss | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _mm_cvtsi64x_ss
dev_langs:
- C++
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e29a914b2cfbc807ac3a0dae8cadc3459d3de23a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="mmcvtsi64xss"></a>_mm_cvtsi64x_ss
**Microsoft 전용**  
  
 생성 된 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 확장 된 버전의 스칼라 단 정밀도 부동 소수점 값으로 변환 하는 64 비트 정수 (`cvtsi2ss`) 명령입니다.  
  
## <a name="syntax"></a>구문  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `a`  
 `__m128` 네 개의 단 정밀도 부동 소수점 값을 포함 하는 구조입니다.  
  
 [in] `b`  
 부동 소수점 값으로 변환 하는 64 비트 정수입니다.  
  
## <a name="return-value"></a>반환 값  
 `__m128` 구조 첫 번째 부동 소수점 값은 변환의 결과입니다. 다른 세 가지 값에서 변경 되지 않고 복사 됩니다 `a`합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`_mm_cvtsi64x_ss`|X64|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 `__m128` 구조 나타냅니다 XMM 레지스터, 이러한 내장 함수 값을 허용 `b` 는 XMM로 이동 될 시스템 메모리에서 등록 합니다.  
  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
## <a name="example"></a>예  
  
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
  
```Output  
54.000000 0.000000 0.000000 0.000000  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__m128](../cpp/m128.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)