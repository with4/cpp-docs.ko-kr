---
title: "_InterlockedCompareExchange128 | Microsoft Docs"
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
  - "_InterlockedCompareExchange128_cpp"
  - "_InterlockedCompareExchange128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cmpxchg16b 명령"
  - "_InterlockedCompareExchange128 내장 함수"
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedCompareExchange128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 128 비트 연동된 된 비교 및 교환을 수행합니다.  
  
## 구문  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### 매개 변수  
 \[in, out\]`Destination`  
 포인터를 대상으로 두 64 비트 정수의 배열입니다 128 비트 필드로 간주 됩니다.  대상 데이터 정렬 일반 보호 오류를 방지 하려면 16 바이트 여야 합니다.  
  
 \[in\] `ExchangeHigh`  
 높은 대상의 부품과 교환 될 수 있는 64 비트 정수입니다.  
  
 \[in\] `ExchangeLow`  
 낮은 대상의 부품과 교환 될 수 있는 64 비트 정수입니다.  
  
 \[in, out\]`ComparandResult`  
 \(128\-비트 필드로 간주\) 두 64 비트 정수 배열로 포인터 대상과 비교 합니다.  출력에서이 대상의 원래 값으로 덮어씁니다.  
  
## 반환 값  
 대상의 원래 값 128 비트 comparand 인 경우 1.  `ExchangeHigh`및 `ExchangeLow` 128 비트 대상 덮어쓰기 합니다.  
  
 comparand는 대상의 원래 값과 일치 하지 않는 경우 0입니다.  대상 값이 변경 되지 않습니다 및를 comparand 값의 대상 값을 덮어쓰게 됩니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 생성의 `cmpxchg16b` 명령 \(와 `lock` 접두사\)는 128 비트 잠긴된 비교 및 교환 수행 하려면.  AMD 64 비트 하드웨어의 초기 버전에이 명령은 지원 하지 않습니다.  하드웨어 지원을 확인 하는 `cmpxchg16b` 명령, 호출의 `__cpuid` 와 내장 `InfoType=0x00000001 (standard function 1)`.  13 비트의 `CPUInfo[2]` \(ECX\) 명령이 지원 되지 않으면 1입니다.  
  
> [!NOTE]
>  값은 `ComparandResult` 항상 덮어쓰게 됩니다.  후의 `lock` , 내장이 즉시 복사 하는 명령의 초기 값은 `Destination` 에 `ComparandResult`.  따라서, `ComparandResult` 및 `Destination` 예기치 않은 동작을 방지 하기 위해 별도 메모리 위치를 가리켜야 합니다.  
  
 사용할 수 있지만 `_InterlockedCompareExchange128` 저급 스레드 동기화에 대 한 작은 동기화 기능을 사용할 수 있는 경우 128 비트가 넘는 동기화 할 필요가 없습니다 \(예: 다른 `_InterlockedCompareExchange` 내장\) 대신.  사용 `_InterlockedCompareExchange128` 원자 액세스 메모리에서 128 비트 값입니다.  
  
 코드를 사용 하 여 내장이 지원 하지 않는 하드웨어에서 실행 하 여 경우는 `cmpxchg16b` 명령의 결과 없는 예측 합니다.  
  
 이 루틴은만 내장로 사용할 수 있습니다.  
  
## 예제  
 이 예제를 사용 하 여 `_InterlockedCompareExchange128` 상위 워드 두 64 비트 정수의 배열입니다 높고 낮은 단어에 해당 합으로 대체 하 고 낮은 단어 증가 합니다.  BigInt.Int 배열에 액세스 원자, 이지만이 예제에서는 단일 스레드를 사용 하 여 및 단순성에 대 한 잠금이 무시.  
  
```  
// cmpxchg16b.c  
// processor: x64  
// compile with: /EHsc /O2  
#include <stdio.h>  
#include <intrin.h>  
  
typedef struct _LARGE_INTEGER_128 {  
    __int64 Int[2];  
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;  
  
volatile LARGE_INTEGER_128 BigInt;  
  
// This AtomicOp() function atomically performs:  
//   BigInt.Int[1] += BigInt.Int[0]  
//   BigInt.Int[0] += 1  
void AtomicOp ()  
{  
    LARGE_INTEGER_128 Comparand;  
    Comparand.Int[0] = BigInt.Int[0];  
    Comparand.Int[1] = BigInt.Int[1];  
    do {  
        ; // nothing  
    } while (_InterlockedCompareExchange128(BigInt.Int,  
                                            Comparand.Int[0] + Comparand.Int[1],  
                                            Comparand.Int[0] + 1,  
                                            Comparand.Int) == 0);  
}  
  
// In a real application, several threads contend for the value  
// of BigInt.  
// Here we focus on the compare and exchange for simplicity.  
int main(void)  
{  
   BigInt.Int[1] = 23;  
   BigInt.Int[0] = 11;  
   AtomicOp();  
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",  
      BigInt.Int[1],BigInt.Int[0]);  
}  
```  
  
  **\[BigInt.Int\[1\] \= 34, BigInt.Int\[0\] \= 12**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_InterlockedCompareExchange 내장 함수](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)