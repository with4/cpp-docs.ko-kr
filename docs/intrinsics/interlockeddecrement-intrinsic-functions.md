---
title: "_InterlockedDecrement Intrinsic Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedDecrement16_rel_cpp"
  - "_InterlockedDecrement16_acq_cpp"
  - "_InterlockedDecrement16_rel"
  - "_InterlockedDecrement64_acq"
  - "_InterlockedDecrement_nf"
  - "_InterlockedDecrement16_nf"
  - "_InterlockedDecrement64_rel_cpp"
  - "_InterlockedDecrement_rel_cpp"
  - "_InterlockedDecrement16_acq"
  - "_InterlockedDecrement64_acq_cpp"
  - "_InterlockedDecrement_rel"
  - "_InterlockedDecrement64_nf"
  - "_InterlockedDecrement16_cpp"
  - "_InterlockedDecrement64"
  - "_InterlockedDecrement_cpp"
  - "_InterlockedDecrement64_rel"
  - "_InterlockedDecrement16"
  - "_InterlockedDecrement"
  - "_InterlockedDecrement64_cpp"
  - "_InterlockedDecrement_acq"
  - "_InterlockedDecrement_acq_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedDecrement intrinsic"
  - "_InterlockedDecrement_acq intrinsic"
  - "_InterlockedDecrement_nf intrinsic"
  - "_InterlockedDecrement_rel intrinsic"
  - "_InterlockedDecrement16 intrinsic"
  - "_InterlockedDecrement16_acq intrinsic"
  - "_InterlockedDecrement16_nf intrinsic"
  - "_InterlockedDecrement16_rel intrinsic"
  - "_InterlockedDecrement64 intrinsic"
  - "_InterlockedDecrement64_acq intrinsic"
  - "_InterlockedDecrement64_nf intrinsic"
  - "_InterlockedDecrement64_rel intrinsic"
  - "InterlockedDecrement intrinsic"
  - "InterlockedDecrement_acq intrinsic"
  - "InterlockedDecrement_rel intrinsic"
  - "InterlockedDecrement16 intrinsic"
  - "InterlockedDecrement64 intrinsic"
  - "InterlockedDecrement64_acq intrinsic"
  - "InterlockedDecrement64_rel intrinsic"
ms.assetid: 5268fce3-86b5-4b2b-b96c-2e531a3fb9b5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _InterlockedDecrement Intrinsic Functions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 Win32 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] [InterlockedDecrement](http://msdn.microsoft.com/library/ms683580.aspx) 함수에 대한 컴파일러 내장 지원을 제공합니다.  
  
## 구문  
  
```  
long _InterlockedDecrement(  
   long * lpAddend  
);  
long _InterlockedDecrement_acq(  
   long * lpAddend  
);  
long _InterlockedDecrement_rel(  
   long * lpAddend  
);  
long _InterlockedDecrement_nf(  
   long * lpAddend  
);  
short _InterlockedDecrement16(  
   short * lpAddend  
);  
short _InterlockedDecrement16_acq(  
   short * lpAddend  
);  
short _InterlockedDecrement16_rel(  
   short * lpAddend  
);  
short _InterlockedDecrement16_nf(  
   short * lpAddend  
);  
__int64 _InterlockedDecrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedDecrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### 매개 변수  
 \[in, out\] `lpAddend`  
 감소시킬 변수에 대한 포인터입니다.  
  
## 반환 값  
 반환 값은 감소된 결과 값입니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_InterlockedDecrement`, `_InterlockedDecrement16`, `_InterlockedDecrement64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 사용되는 데이터 형식과 프로세서별 획득 또는 해제 의미 체계에 따라 다른 `_InterlockedDecrement`의 여러 변형이 있습니다.  
  
 `_InterlockedDecrement` 함수는 32비트 정수 값에 대해 작동하는 반면 `_InterlockedDecrement16`은 16비트 정수 값에 대해, `_InterlockedDecrement64`는 64비트 정수 값에 대해 작동합니다.  
  
 ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다.  `_nf`\("no fence"의 약어\) 접미사가 포함된 내장 함수는 메모리 장벽으로 작동하지 않습니다.  
  
 `lpAddend` 매개 변수가 가리키는 변수는 32비트 경계에 정렬되어야 합니다. 그렇지 않으면 다중 프로세서 x86 시스템과 x86이 아닌 시스템에서 이 함수가 실패합니다.  자세한 내용은 [align](../cpp/align-cpp.md)을 참조하세요.  
  
 이러한 루틴은 내장 함수로만 사용할 수 있습니다.  
  
## 예제  
  
```  
// compiler_intrinsics_interlocked.cpp  
// compile with: /Oi  
#define _CRT_RAND_S  
  
#include <cstdlib>  
#include <cstdio>  
#include <process.h>  
#include <windows.h>  
  
// To declare an interlocked function for use as an intrinsic,  
// include intrin.h and put the function in a #pragma intrinsic   
// statement.  
#include <intrin.h>  
  
#pragma intrinsic (_InterlockedIncrement)  
  
// Data to protect with the interlocked functions.  
volatile LONG data = 1;  
  
void __cdecl SimpleThread(void* pParam);  
  
const int THREAD_COUNT = 6;  
  
int main() {  
   DWORD num;  
   HANDLE threads[THREAD_COUNT];  
   int args[THREAD_COUNT];  
   int i;  
  
   for (i = 0; i < THREAD_COUNT; i++) {  
     args[i] = i + 1;  
     threads[i] = reinterpret_cast<HANDLE>(_beginthread(SimpleThread, 0,   
                           args + i));  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
         // error creating threads  
         break;  
   }  
  
   WaitForMultipleObjects(i, threads, true, INFINITE);  
}  
  
// Code for our simple thread  
void __cdecl SimpleThread(void* pParam) {  
   int threadNum = *((int*)pParam);  
   int counter;  
   unsigned int randomValue;  
   unsigned int time;  
   errno_t err = rand_s(&randomValue);  
  
   if (err == 0) {  
      time = (unsigned int) ((double) randomValue / (double) UINT_MAX * 500);  
      while (data < 100) {  
         if (data < 100) {  
            _InterlockedIncrement(&data);  
            printf_s("Thread %d: %d\n", threadNum, data);  
         }  
  
         Sleep(time);   // wait up to half of a second  
      }  
   }  
  
   printf_s("Thread %d complete: %d\n", threadNum, data);  
}  
```  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)