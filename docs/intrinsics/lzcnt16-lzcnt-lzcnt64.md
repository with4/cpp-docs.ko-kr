---
title: __lzcnt16, __lzcnt, __lzcnt64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85af6534ccf578bccabcd0f7b517234b2b560b6f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64
**Microsoft 전용**  
  
 개수 앞에 오는 수는 16, 32 비트 또는 64 바이트 정수에 0입니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `value`  
 16-, 32 또는 64 비트 부호 없는 정수 앞에 오는 0에 대 한 검색입니다.  
  
## <a name="return-value"></a>반환 값  
 앞에 있는 0 비트의 수는 `value` 매개 변수입니다. 경우 `value` 가 0 이면 반환 값 (16, 32 또는 64) 입력된 피연산자의 크기입니다. 이면 가장 중요 한 비트가 `value` 1이 반환 값은 0입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__lzcnt16`|AMD: 고급 비트 조작을 (ABM)<br /><br /> Intel: Haswell|  
|`__lzcnt`|AMD: 고급 비트 조작을 (ABM)<br /><br /> Intel: Haswell|  
|`__lzcnt64`|AMD: 64 비트 모드에서 비트 조작 (ABM) 고급합니다.<br /><br /> Intel: Haswell|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 각각의 이러한 내장 함수 생성의 `lzcnt` 명령입니다.  값의 크기는는 `lzcnt` 해당 인수의 크기와 같습니다 반환 하는 명령입니다.  32 비트 모드에서 발생 하는 없는 64 비트 범용 레지스터, 따라서 더 64 비트 `lzcnt`합니다.  
  
 에 대 한 하드웨어 지원을 확인 하는 `lzcnt` 명령 호출은 `__cpuid` 포함 된 내장 함수 `InfoType=0x80000001` 의 5 비트를 확인 하 고 `CPUInfo[2] (ECX)`합니다. 그렇지 않으면이 비트는 명령의 지원 되 면 1과 0 수 있습니다. 하는 경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어에는 `lzcnt` 명령 결과 예측할 수 없습니다.  
  
 Intel 프로세서를 지원 하지 않는 `lzcnt` 명령으로 실행 명령 바이트 인코딩을 `bsr` (스캔 역방향 비트)입니다. 사용 하 여 코드 이식성 중요 한 경우는 `_BitScanReverse` 내장 함수 대신 합니다. 자세한 내용은 참조 [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md)합니다.  
  
## <a name="example"></a>예  
  
```  
// Compile this test with: /EHsc  
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
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__lzcnt16(0x0) = 16  
__lzcnt16(0xff) = 8  
__lzcnt16(0xffff) = 0  
__lzcnt(0x0) = 32  
__lzcnt(0xff) = 24  
__lzcnt(0xffff) = 16  
__lzcnt(0xffffffff) = 0  
```  
  
**Microsoft 전용 종료**  
 이 콘텐츠의 일부는 고급 마이크로 장치, inc 2007 저작권 All rights reserved. 고급 마이크로 장치, Inc. 로부터 사용 권한을 승인 하에 복제  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)