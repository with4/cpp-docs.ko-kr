---
title: "_InterlockedExchange Intrinsic Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedExchange_rel"
  - "_InterlockedExchange8_nf"
  - "_InterlockedExchange_acq_cpp"
  - "_InterlockedExchange_nf"
  - "_InterlockedExchange64_nf"
  - "_InterlockedExchange_HLEAcquire"
  - "_InterlockedExchange_cpp"
  - "_InterlockedExchange64_acq_cpp"
  - "_InterlockedExchange64_acq"
  - "_InterlockedExchange64_HLERelease"
  - "_InterlockedExchange8_acq"
  - "_InterlockedExchange16_acq"
  - "_InterlockedExchange"
  - "_InterlockedExchange64_HLEAcquire"
  - "_InterlockedExchange8"
  - "_InterlockedExchange64_rel"
  - "_InterlockedExchange_acq"
  - "_InterlockedExchange16"
  - "_InterlockedExchange16_rel"
  - "_InterlockedExchange16_nf"
  - "_InterlockedExchange64"
  - "_InterlockedExchange_HLERelease"
  - "_InterlockedExchange64_cpp"
  - "_InterlockedExchange8_rel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedExchange intrinsic"
  - "_InterlockedExchange_acq intrinsic"
  - "_InterlockedExchange16"
  - "_InterlockedExchange16_acq"
  - "_InterlockedExchange16_nf"
  - "_InterlockedExchange16_rel"
  - "_InterlockedExchange64 intrinsic"
  - "_InterlockedExchange64_acq intrinsic"
  - "_InterlockedExchange8"
  - "_InterlockedExchange8_acq"
  - "_InterlockedExchange8_nf"
  - "_InterlockedExchange8_rel"
  - "InterlockedExchange intrinsic"
  - "InterlockedExchange_acq intrinsic"
  - "InterlockedExchange64 intrinsic"
  - "InterlockedExchange64_acq intrinsic"
ms.assetid: be2f232a-6301-462a-a92b-fcdeb8b0f209
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _InterlockedExchange Intrinsic Functions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 지정된 값을 설정하는 원자성 명령을 생성합니다.  
  
## 구문  
  
```  
long _InterlockedExchange(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_acq(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLEAcquire(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLERelease(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_nf(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_rel(  
   long volatile * Target,  
   long Value  
);  
char _InterlockedExchange8(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_acq(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_nf(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_rel(  
   char volatile * Target,  
   char Value  
);  
short _InterlockedExchange16(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_acq(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_nf(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_rel(  
   short volatile * Target,  
   short Value  
);  
__int64 _InterlockedExchange64(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_acq(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLEAcquire(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLERelease(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_nf(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_rel(  
   __int64 volatile * Target,  
   __int64 Value  
);  
```  
  
#### 매개 변수  
 \[in, out\] `Target`  
 교환할 값에 대한 포인터입니다.  함수는 이 변수를 `Value`로 설정하고 이전 값을 반환합니다.  
  
 \[in\] `Value`  
 `Target`이 가리키는 값과 교환할 값입니다.  
  
## 반환 값  
 `Target`이 가리키는 초기 값을 반환합니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|머리글|  
|-----------|----------|---------|  
|`_InterlockedExchange`, `_InterlockedExchange8`, `_InterlockedExchange16`, `_InterlockedExchange64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchange_acq`, `_InterlockedExchange_nf`, `_InterlockedExchange_rel`, `_InterlockedExchange8_acq`, `_InterlockedExchange8_nf`, `_InterlockedExchange8_rel`, `_InterlockedExchange16_acq`, `_InterlockedExchange16_nf`, `_InterlockedExchange16_rel`, `_InterlockedExchange64_acq`, `_InterlockedExchange64_nf`, `_InterlockedExchange64_rel`,|ARM|\<intrin.h\>|  
|`_InterlockedExchange_HLEAcquire`, `_InterlockedExchange_HLERelease`, `_InterlockedExchange64_HLEAcquire`, `_InterlockedExchange64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 설명  
 `_InterlockedExchange`는 Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedExchange](http://msdn.microsoft.com/library/ms683590.aspx) 함수에 대한 컴파일러 내장 지원을 제공합니다.  
  
 사용되는 데이터 형식과 프로세서별 획득 또는 해제 의미 체계에 따라 다른 `_InterlockedExchange`의 여러 변형이 있습니다.  
  
 `_InterlockedExchange` 함수는 32비트 정수 값에 대해 작동하는 반면 `_InterlockedExchange8`은 8비트 정수 값에 대해, `_InterlockedExchange16`은 16비트 정수 값에 대해, 그리고 `_InterlockedExchange64`는 64비트 정수 값에 대해 작동합니다.  
  
 ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다.  `_nf`\("no fence"의 약어\) 접미사가 포함된 내장 함수는 메모리 장벽으로 작동하지 않습니다.  
  
 HLE\(Hardware Lock Elision\) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다.  HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.  
  
 이러한 루틴은 내장 함수로만 사용할 수 있습니다.  
  
## 예제  
 `_InterlockedExchange`를 사용하는 방법의 샘플은 [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)를 참조하세요.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)