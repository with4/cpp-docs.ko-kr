---
title: "_InterlockedOr 내장 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _InterlockedOr8_nf
- _InterlockedOr_HLEAcquire
- _InterlockedOr16_nf
- _InterlockedOr64
- _InterlockedOr8_np
- _InterlockedOr64_cpp
- _InterlockedOr8_acq
- _InterlockedOr_nf
- _InterlockedOr64_acq
- _InterlockedOr_np
- _InterlockedOr8
- _InterlockedOr
- _InterlockedOr64_np
- _InterlockedOr_acq
- _InterlockedOr64_HLERelease
- _InterlockedOr16_np
- _InterlockedOr_cpp
- _InterlockedOr8_rel
- _InterlockedOr64_rel
- _InterlockedOr16_acq
- _InterlockedOr_rel
- _InterlockedOr16_rel
- _InterlockedOr_HLERelease
- _InterlockedOr64_HLEAcquire
- _InterlockedOr16
- _InterlockedOr64_nf
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedOr_acq intrinsic
- InterlockedOr64 intrinsic
- _InterlockedOr_nf intrinsic
- _InterlockedOr intrinsic
- _InterlockedOr64_HLERelease intrinsic
- _InterlockedOr8_rel intrinsic
- _InterlockedOr8_np intrinsic
- _InterlockedOr64_nf intrinsic
- _InterlockedOr_HLERelease intrinsic
- _InterlockedOr16_np intrinsic
- InterlockedOr intrinsic
- _InterlockedOr8_nf intrinsic
- _InterlockedOr16_nf intrinsic
- _InterlockedOr8_acq intrinsic
- _InterlockedOr64 intrinsic
- _InterlockedOr16 intrinsic
- _InterlockedOr64_acq intrinsic
- _InterlockedOr64_HLEAcquire intrinsic
- _InterlockedOr_np intrinsic
- _InterlockedOr64_rel intrinsic
- _InterlockedOr64_np intrinsic
- _InterlockedOr_rel intrinsic
- _InterlockedOr8 intrinsic
- _InterlockedOr16_acq intrinsic
- _InterlockedOr16_rel intrinsic
- _InterlockedOr_HLEAcquire intrinsic
ms.assetid: 5f265240-7af8-44b7-b952-19f3a9c56186
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44949aad405fbfdad776548a73a3152595ffa158
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="interlockedor-intrinsic-functions"></a>_InterlockedOr Intrinsic Functions
**Microsoft 전용**  
  
 여러 스레드가 공유하는 변수에 대해 원자성 비트 OR 작업을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
long _InterlockedOr(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_acq(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_HLEAcquire(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_HLERelease(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_nf(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_np(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_rel(  
   long volatile * Value,  
   long Mask  
);  
char _InterlockedOr8(  
   char volatile * Value,  
   long Mask  
);  
char _InterlockedOr8_acq(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedOr8_nf(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedOr8_np(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedOr8_rel(  
   char volatile * Value,  
   char Mask  
);  
short _InterlockedOr16(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_acq(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_nf(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_np(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_rel(  
   short volatile * Value,  
   short Mask  
);  
__int64 _InterlockedOr64(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_acq(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedOr64_HLEAcquire(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_HLERelease(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedOr64_nf(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_np(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_rel(  
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
 첫 번째 매개 변수가 가리키는 원래 값입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|머리글|  
|---------------|------------------|------------|  
|`_InterlockedOr`, `_InterlockedOr8`, `_InterlockedOr16`, `_InterlockedOr64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedOr_acq`, `_InterlockedOr_nf`, `_InterlockedOr_rel`, `_InterlockedOr8_acq`, `_InterlockedOr8_nf`, `_InterlockedOr8_rel`, `_InterlockedOr16_acq`, `_InterlockedOr16_nf`, `_InterlockedOr16_rel`, `_InterlockedOr64_acq`, `_InterlockedOr64_nf`, `_InterlockedOr64_rel`|ARM|\<intrin.h>|  
|`_InterlockedOr_np`, `_InterlockedOr8_np`, `_InterlockedOr16_np`, `_InterlockedOr64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedOr_HLEAcquire`, `_InterlockedOr_HLERelease`, `_InterlockedOr64_HLEAcquire`, `_InterlockedOr64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h>|  
  
## <a name="remarks"></a>설명  
 각 함수 이름의 숫자는 인수의 비트 크기를 지정합니다.  
  
 ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다. `_nf`("no fence"의 약어) 접미사가 포함된 ARM 내장 함수는 메모리 장벽으로 작동하지 않습니다.  
  
 `_np`("no prefetch"의 약어) 접미사가 포함된 내장 함수는 컴파일러가 가능한 프리페치 연산을 삽입하지 못하도록 차단합니다.  
  
 HLE(Hardware Lock Elision) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다. HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.  
  
## <a name="example"></a>예  
  
```  
// _InterlockedOr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedOr)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedOr(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
```Output  
0xffffff00 0xffff00 0xff00ff00  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)