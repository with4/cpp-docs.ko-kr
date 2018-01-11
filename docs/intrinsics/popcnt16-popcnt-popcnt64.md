---
title: __popcnt16, __popcnt, __popcnt64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
dev_langs: C++
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45e60a412dc24f685fd375ebc19c109b2bee0e2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64
**Microsoft 전용**  
  
 개수를 하나의 비트 (채우기 수)는 16, 32 비트 또는 64 비트 부호 없는 정수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `value`  
 16-, 32 또는 64 비트 부호 없는 정수 모집단 count 하겠습니다.  
  
## <a name="return-value"></a>반환 값  
 하나의 비트 수는 `value` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__popcnt16`|고급 비트 조작|  
|`__popcnt`|고급 비트 조작|  
|`__popcnt64`|64 비트 모드에서 고급 비트 조작 합니다.|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 각각의 이러한 내장 함수 생성의 `popcnt` 명령입니다.  값의 크기는는 `popcnt` 해당 인수의 크기와 같습니다 반환 하는 명령입니다.  32 비트 모드에서 발생 하는 없는 64 비트 범용 레지스터, 따라서 더 64 비트 `popcnt`합니다.  
  
 에 대 한 하드웨어 지원을 확인 하는 `popcnt` 명령, 호출의 `__cpuid` 포함 된 내장 함수 `InfoType=0x00000001` 의 23 비트를 확인 하 고 `CPUInfo[2] (ECX)`합니다. 이 비트는 그렇지 않으면 명령이 지원 되 면 1과 0입니다. 하는 경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어에는 `popcnt` 명령 결과 예측할 수 없습니다.  
  
## <a name="example"></a>예  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__popcnt16(0x0) = 0  
__popcnt16(0xff) = 8  
__popcnt16(0xffff) = 16  
__popcnt(0x0) = 0  
__popcnt(0xff) = 8  
__oopcnt(0xffff) = 16  
__popcnt(0xffffffff) = 32  
```  
  
**Microsoft 전용 종료**  
 고급 마이크로 장치, inc 2007 저작권 All rights reserved. 고급 마이크로 장치, Inc. 로부터 사용 권한을 승인 하에 복제  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)