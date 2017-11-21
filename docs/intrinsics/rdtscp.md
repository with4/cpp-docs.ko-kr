---
title: __rdtscp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __rdtscp
dev_langs: C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 697b06bcddbaadb8c3a8a1dece761cdf31a31527
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="rdtscp"></a>__rdtscp
**Microsoft 전용**  
  
 생성의 `rdtscp` 명령 기록 `TSC_AUX[31:0`], 메모리 및 64 비트 타임 스탬프 카운터 반환에 (`TSC)` 결과입니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `Aux`  
 컴퓨터별 레지스터의 내용을 포함 하는 위치에 대 한 포인터 `TSC_AUX[31:0]`합니다.  
  
## <a name="return-value"></a>반환 값  
 64 비트 부호 없는 정수 틱 수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__rdtscp`|AMD NPT 제품군 0Fh 또는 이후 버전|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 이 내장 함수 생성의 `rdtscp` 명령입니다. 이 명령에 대 한 하드웨어 지원을 확인 하려면 호출는 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 의 27 비트를 확인 하 고 `CPUInfo[3] (EDX)`합니다. 이 비트는 그렇지 않으면 명령이 지원 되 면 1과 0입니다.  하는 경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어에는 `rdtscp` 명령 결과 예측할 수 없습니다.  
  
> [!CAUTION]
>  와 달리 `rdtsc`, `rdtscp` 은 직렬화 명령; 컴파일러에서이 관련 된 코드를 이동할 수는 그럼에도 불구 하 고 내장 함수입니다.  
  
 이전 버전의이 세대의 하드웨어에 TSC 값의 해석 다른 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]합니다.  자세한 내용은 하드웨어 설명서를 참조 하십시오.  
  
 에 있는 값의 의미 `TSC_AUX[31:0]` 운영 체제에 따라 달라 집니다.  
  
## <a name="example"></a>예제  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
```Output  
3363423610155519 ticks  
TSC_AUX was 0  
```  
  
**Microsoft 전용 종료**  
 고급 마이크로 장치, inc 2007 저작권 All rights reserved. 고급 마이크로 장치, Inc. 로부터 사용 권한을 승인 하에 복제  
  
## <a name="see-also"></a>참고 항목  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)