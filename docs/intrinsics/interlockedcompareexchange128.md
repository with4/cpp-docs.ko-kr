---
title: _InterlockedCompareExchange128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
dev_langs: C++
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0cbf4e29e02670b4532a4be82864cf3cf040df73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128
**Microsoft 전용**  
  
 128 비트 연관된 비교 및 교환을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in, out] `Destination`  
 두 개의 64 비트 정수 배열 대상에 대 한 포인터를 128 비트 필드로 간주 합니다. 대상 데이터에 일반 보호 오류를 방지 하기 위해 정렬 16 바이트 여야 합니다.  
  
 [in] `ExchangeHigh`  
 대상의 상위 부분으로 교환할 수 있는 64 비트 정수입니다.  
  
 [in] `ExchangeLow`  
 대상의 하위 부분으로 교환할 수 있는 64 비트 정수입니다.  
  
 [in, out] `ComparandResult`  
 (128 비트 필드로 간주)는 두 개의 64 비트 정수 배열에 대 한 포인터를 대상으로 비교 합니다.  출력에는 대상의 원래 값으로 덮어쓰며이 합니다.  
  
## <a name="return-value"></a>반환 값  
 128 비트 피비교수와 대상의 원래 값이 일치 하는 경우 1입니다. `ExchangeHigh`및 `ExchangeLow` 128 비트 대상 덮어쓰기.  
  
 비교 피연산자는 대상의 원래 값과 일치 하지 않는 경우 0입니다. 대상의 값이 변경 되지 하 고 대상의 값과 비교 피연산자의 값을 덮어씁니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 이 내장 함수 생성의 `cmpxchg16b` 명령 (으로 `lock` 접두사) 128 비트 잠긴된 비교 및 교환 수행 하 합니다. AMD 64 비트 하드웨어의 초기 버전에는이 명령을 지원 하지 않습니다. 에 대 한 하드웨어 지원을 확인 하 고 `cmpxchg16b` 명령, 호출의 `__cpuid` 포함 된 내장 함수 `InfoType=0x00000001 (standard function 1)`합니다. 13 비트 `CPUInfo[2]` (ECX)는 명령이 지원 되는 경우 1이 됩니다.  
  
> [!NOTE]
>  값 `ComparandResult` 항상 덮어씁니다. 후의 `lock` 의 초기 값은 즉시 복사 하는 명령,이 내장 `Destination` 를 `ComparandResult`합니다. 이러한 이유로 `ComparandResult` 및 `Destination` 예기치 않은 동작을 방지 하기 위해 개별 메모리 위치를 가리켜야 합니다.  
  
 사용할 수 있지만 `_InterlockedCompareExchange128` 하위 수준 스레드 동기화에 대 한 불필요 더 작은 동기화 함수를 사용할 수 있는 경우 128 비트 이상 동기화 할 (다른 같은 `_InterlockedCompareExchange` 내장 함수) 대신. 사용 하 여 `_InterlockedCompareExchange128` 메모리에 128 비트 값에 대 한 원자성 액세스 하려는 경우.  
  
 하는 경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어에는 `cmpxchg16b` 명령 결과 예측할 수 없습니다.  
  
 이 루틴은 내장 함수로 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 이 예에서는 `_InterlockedCompareExchange128` 두 개의 64 비트 정수 배열의 높은 단어는 고가 및 저가 단어의 합으로 컨트롤러를 바꾸려면 낮은 단어 증가 합니다. BigInt.Int 배열에 대 한 액세스가 원자성을 하지만이 예제에서는 단일 스레드를 사용 하 고 단순성에 대 한 잠금을 무시 합니다.  
  
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
  
```Output  
BigInt.Int[1] = 34, BigInt.Int[0] = 12  
```  
  
**Microsoft 전용 종료**  
 고급 마이크로 장치, inc 2007 저작권 All rights reserved. 고급 마이크로 장치, Inc. 로부터 사용 권한을 승인 하에 복제  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [_InterlockedCompareExchange 내장 함수](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)