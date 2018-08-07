---
title: 내장 함수가 _InterlockedXor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedXor_nf
- _InterlockedXor_np
- _InterlockedXor64_HLERelease
- _InterlockedXor8_acq
- _InterlockedXor64_acq
- _InterlockedXor64_rel
- _InterlockedXor64_nf
- _InterlockedXor_acq
- _InterlockedXor16
- _InterlockedXor64_np
- _InterlockedXor64
- _InterlockedXor_HLEAcquire
- _InterlockedXor_HLERelease
- _InterlockedXor_cpp
- _InterlockedXor16_rel
- _InterlockedXor8_rel
- _InterlockedXor8
- _InterlockedXor64_HLEAcquire
- _InterlockedXor16_nf
- _InterlockedXor16_acq
- _InterlockedXor16_np
- _InterlockedXor8_fn
- _InterlockedXor8_np
- _InterlockedXor64_cpp
- _InterlockedXor_rel
- _InterlockedXor
dev_langs:
- C++
helpviewer_keywords:
- InterlockedXor intrinsic
- _InterlockedXor64 intrinsic
- InterlockedXor64 intrinsic
- _InterlockedXor intrinsic
ms.assetid: faef1796-cb5a-4430-b1e2-9d5eaf9b4a91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dea8e222660825824c8dc02405832da4395b69f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334125"
---
# <a name="interlockedxor-intrinsic-functions"></a>_InterlockedXor Intrinsic Functions
**Microsoft 전용**  
  
 여러 스레드에서 공유하는 변수에 대해 원자성 XOR(단독 OR) 작업을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
long _InterlockedXor(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_acq(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_HLEAcquire(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_HLERelease(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_nf(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_np(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_rel(  
   long volatile * Value,  
   long Mask  
);  
char _InterlockedXor8(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_acq(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_nf(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_np(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_rel(  
   char volatile * Value,  
   char Mask  
);  
short _InterlockedXor16(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_acq(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_nf (  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_np (  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_rel(  
   short volatile * Value,  
   short Mask  
);  
__int64 _InterlockedXor64(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_acq(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedXor64_HLEAcquire(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_HLERelease(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedXor64_nf(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_np(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_rel(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in, out] `Value`  
 첫 번째 피연산자에 대한 포인터입니다(결과로 바뀜).  
  
 [in] `Mask`  
 두 번째 피연산자입니다.  
  
## <a name="return-value"></a>반환 값  
 첫 번째 피연산자의 원래 값입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|머리글|  
|---------------|------------------|------------|  
|`_InterlockedXor`, `_InterlockedXor8`, `_InterlockedXor16`, `_InterlockedXor64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedXor_acq`, `_InterlockedXor_nf`, `_InterlockedXor_rel`, `_InterlockedXor8_acq`, `_InterlockedXor8_nf`, `_InterlockedXor8_rel`, `_InterlockedXor16_acq`, `_InterlockedXor16_nf`, `_InterlockedXor16_rel`, `_InterlockedXor64_acq`, `_InterlockedXor64_nf`, `_InterlockedXor64_rel`,|ARM|\<intrin.h>|  
|`_InterlockedXor_np`, `_InterlockedXor8_np`, `_InterlockedXor16_np`, `_InterlockedXor64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedXor_HLEAcquire`, `_InterlockedXor_HLERelease`, `_InterlockedXor64_HLEAcquire`, `_InterlockedXor64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h>|  
  
## <a name="remarks"></a>설명  
 각 함수 이름의 숫자는 인수의 비트 크기를 지정합니다.  
  
 ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다. `_nf`("no fence"의 약어) 접미사가 포함된 ARM 내장 함수는 메모리 장벽으로 작동하지 않습니다.  
  
 `_np`("no prefetch"의 약어) 접미사가 포함된 내장 함수는 컴파일러가 가능한 프리페치 연산을 삽입하지 못하도록 차단합니다.  
  
 HLE(Hardware Lock Elision) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다. HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.  
  
## <a name="example"></a>예제  
  
```  
// _InterLockedXor.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedXor)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedXor(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
```Output  
0xffff0000 0xffff00 0xff00ff00  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)