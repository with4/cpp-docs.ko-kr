---
title: _mm_cvtss_si64x | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtss_si64x
dev_langs:
- C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665c52fc0dd0645e25d3014cc28f9fdfba344e2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332106"
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Microsoft 전용**  
  
 생성 된 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 된 변환 스칼라 단일 정밀도 부동 소수점 숫자의 64 비트 정수로 확장 된 버전 (`cvtss2si`) 명령입니다.  
  
## <a name="syntax"></a>구문  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `value`  
 `__m128` 부동 소수점 값을 포함 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 64 비트 정수를 첫 번째 부동 소수점 값을 정수로 변환의 결과입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 구조 값의 첫 번째 요소는 정수로 변환 하 고 반환 됩니다. MXCSR에서 반올림 제어 비트는 반올림 동작을 결정 하는 데 사용 됩니다. 반올림 모드에는 기본값이 round를 가장 가까운, 소수 부분은 0.5 경우 숫자를 반올림 합니다. 때문에 `__m128` 구조 XMM 레지스터에서 XMM 레지스터는이 내장 함수는 값을 나타내는 시스템 메모리에 기록 합니다.  
  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
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
  
```Output  
101  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__m128d](../cpp/m128d.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)