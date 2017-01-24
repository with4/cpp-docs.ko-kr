---
title: "_InterlockedCompareExchangePointer Intrinsic Functions | Microsoft Docs"
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
  - "_InterlockedCompareExchangePointer_HLERelease"
  - "_InterlockedCompareExchangePointer_rel"
  - "_InterlockedCompareExchangePointer_acq_cpp"
  - "_InterlockedCompareExchangePointer"
  - "_InterlockedCompareExchangePointer_cpp"
  - "_InterlockedCompareExchangePointer_np"
  - "_InterlockedCompareExchangePointer_rel_cpp"
  - "_InterlockedCompareExchangePointer_HLEAcquire"
  - "_InterlockedCompareExchangePointer_acq"
  - "_InterlockedCompareExchangePointer_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedCompareExchangePointer intrinsic"
  - "_InterlockedCompareExchangePointer_acq intrinsic"
  - "_InterlockedCompareExchangePointer_HLEAcquire intrinsic"
  - "_InterlockedCompareExchangePointer_HLERelease intrinsic"
  - "_InterlockedCompareExchangePointer_nf intrinsic"
  - "_InterlockedCompareExchangePointer_np intrinsic"
  - "_InterlockedCompareExchangePointer_rel intrinsic"
  - "InterlockedCompareExchangePointer intrinsic"
  - "InterlockedCompareExchangePointer_acq intrinsic"
  - "InterlockedCompareExchangePointer_rel intrinsic"
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedCompareExchangePointer Intrinsic Functions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `Comparand` 및 `Destination` 주소가 같으면 `Destination` 주소에 `Exchange` 주소를 저장하는 원자성 작업을 수행합니다.  
  
## 구문  
  
```  
void * _InterlockedCompareExchangePointer (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_acq (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLEAcquire (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLERelease (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_nf (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_np (    void * volatile * Destination,    void * Exchange,    void * Comparand ); long _InterlockedCompareExchangePointer_rel (    void * volatile * Destination,    void * Exchange,    void * Comparand );  
```  
  
#### 매개 변수  
 \[in, out\] `Destination`  
 대상 값에 대한 포인터의 포인터입니다.  부호는 무시됩니다.  
  
 \[in\] `Exchange`  
 Exchange 포인터입니다.  부호는 무시됩니다.  
  
 \[in\] `Comparand`  
 대상과 비교할 포인터입니다.  부호는 무시됩니다.  
  
## 반환 값  
 반환 값은 대상의 초기 값입니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|Header|  
|-----------|----------|------------|  
|`_InterlockedCompareExchangePointer`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h\>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 설명  
 `_InterlockedCompareExchangePointer`는 `Destination` 주소와 `Comparand` 주소의 원자성 비교를 수행합니다.  `Destination` 주소가 `Comparand` 주소와 같으면 `Destination`으로 지정된 주소에 `Exchange` 주소가 저장됩니다.  그렇지 않으면 작업이 수행되지 않습니다.  
  
 `_InterlockedCompareExchangePointer`는 Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx) 함수에 대한 컴파일러 내장 함수 지원을 제공합니다.  
  
 `_InterlockedCompareExchangePointer`를 사용하는 방법의 예제는 [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)를 참조하세요.  
  
 ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다.  `_nf`\("no fence"의 약어\) 접미사가 포함된 ARM 내장 함수는 메모리 장벽으로 작동하지 않습니다.  
  
 `_np`\("no prefetch"의 약어\) 접미사가 포함된 내장 함수는 컴파일러가 가능한 프리페치 연산을 삽입하지 못하도록 차단합니다.  
  
 HLE\(Hardware Lock Elision\) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다.  HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.  
  
 이러한 루틴은 내장 함수로만 사용할 수 있습니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)