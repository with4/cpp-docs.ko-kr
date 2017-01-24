---
title: "_InterlockedExchangeAdd Intrinsic Functions | Microsoft Docs"
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
  - "_InterlockedExchangeAdd64_nf"
  - "_InterlockedExchangeAdd64_rel"
  - "_InterlockedExchangeAdd16_rel"
  - "_InterlockedExchangeAdd_acq"
  - "_InterlockedExchangeAdd_nf"
  - "_InterlockedExchangeAdd_rel"
  - "_InterlockedExchangeAdd8_acq"
  - "_InterlockedExchangeAdd16_nf"
  - "_InterlockedExchangeAdd_acq_cpp"
  - "_InterlockedExchangeAdd64_acq_cpp"
  - "_InterlockedExchangeAdd16_acq"
  - "_InterlockedExchangeAdd_HLERelease"
  - "_InterlockedExchangeAdd64_cpp"
  - "_InterlockedExchangeAdd64_HLERelease"
  - "_InterlockedExchangeAdd64_acq"
  - "_InterlockedExchangeAdd8"
  - "_InterlockedExchangeAdd64"
  - "_InterlockedExchangeAdd8_nf"
  - "_InterlockedExchangeAdd16"
  - "_InterlockedExchangeAdd64_rel_cpp"
  - "_InterlockedExchangeAdd_cpp"
  - "_InterlockedExchangeAdd8_rel"
  - "_InterlockedExchangeAdd_HLEAcquire"
  - "_InterlockedExchangeAdd64_HLEAcquire"
  - "_InterlockedExchangeAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedExchangeAdd intrinsic"
  - "_InterlockedExchangeAdd_acq intrinsic"
  - "_InterlockedExchangePointer intrinsic"
  - "_InterlockedExchangePointer intrinsic"
  - "_InterlockedExchangeAdd_nf intrinsic"
  - "_InterlockedExchangeAdd_rel intrinsic"
  - "_InterlockedExchangeAdd16 intrinsic"
  - "_InterlockedExchangeAdd16_acq intrinsic"
  - "_InterlockedExchangeAdd16_nf intrinsic"
  - "_InterlockedExchangeAdd16_rel intrinsic"
  - "_InterlockedExchangeAdd64 intrinsic"
  - "_InterlockedExchangeAdd64_acq intrinsic"
  - "_InterlockedExchangePointer intrinsic"
  - "_InterlockedExchangePointer intrinsic"
  - "_InterlockedExchangeAdd64_nf intrinsic"
  - "_InterlockedExchangeAdd64_rel intrinsic"
  - "_InterlockedExchangeAdd8 intrinsic"
  - "_InterlockedExchangeAdd8_acq intrinsic"
  - "_InterlockedExchangeAdd8_nf intrinsic"
  - "_InterlockedExchangeAdd8_rel intrinsic"
  - "InterlockedExchangeAdd intrinsic"
  - "InterlockedExchangeAdd_acq intrinsic"
  - "InterlockedExchangeAdd_rel intrinsic"
  - "InterlockedExchangeAdd64 intrinsic"
  - "InterlockedExchangeAdd64_acq intrinsic"
  - "InterlockedExchangeAdd64_rel intrinsic"
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedExchangeAdd Intrinsic Functions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedExchangeAdd Intrinsic Functions](../intrinsics/interlockedexchangeadd-intrinsic-functions.md) 함수에 대한 컴파일러 내장 함수 지원을 제공합니다.  
  
## 구문  
  
```  
long _InterlockedExchangeAdd(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_acq(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_rel(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_nf(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLEAcquire(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLERelease(    long volatile * Addend,    long Value ); char _InterlockedExchangeAdd8(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_acq(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_rel(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_nf(    char volatile * Addend,    char Value ); short _InterlockedExchangeAdd16(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_acq(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_rel(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_nf(    short volatile * Addend,    short Value ); __int64 _InterlockedExchangeAdd64(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_acq(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_rel(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_nf(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLEAcquire(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLERelease(    __int64 volatile * Addend,    __int64 Value );   
```  
  
#### 매개 변수  
 \[in, out\] `Addend`  
 추가 대상 값입니다\(추가 결과로 바뀜\).  
  
 \[in\] `Value`  
 추가할 값입니다.  
  
## 반환 값  
 반환 값은 `Addend` 매개 변수가 가리키는 변수의 초기 값입니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|Header|  
|-----------|----------|------------|  
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\<intrin.h\>|  
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 설명  
 사용되는 데이터 형식과 프로세서별 획득 또는 해제 의미 체계에 따라 다른 `_InterlockedExchangeAdd`의 여러 변형이 있습니다.  
  
 `_InterlockedExchangeAdd` 함수는 32비트 정수 값에 대해 작동하는 반면 `_InterlockedExchangeAdd8`은 8비트 정수 값에 대해, `_InterlockedExchangeAdd16`은 16비트 정수 값에 대해, 그리고 `_InterlockedExchangeAdd64`는 64비트 정수 값에 대해 작동합니다.  
  
 ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다.  `_nf`\("no fence"의 약어\) 접미사가 포함된 내장 함수는 메모리 장벽으로 작동하지 않습니다.  
  
 HLE\(Hardware Lock Elision\) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다.  HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.  
  
 이러한 루틴은 내장 함수로만 사용할 수 있습니다.  즉, [\/Oi](../build/reference/oi-generate-intrinsic-functions.md) 또는 [\#pragma 내장 함수](../preprocessor/intrinsic.md) 사용 여부에 관계없이 이러한 루틴은 내장 함수입니다.  이러한 내장 함수에 대해서는 [\#pragma 함수](../preprocessor/function-c-cpp.md)를 사용할 수 없습니다.  
  
## 예제  
 `_InterlockedExchangeAdd`를 사용하는 방법의 샘플은 [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)를 참조하세요.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)