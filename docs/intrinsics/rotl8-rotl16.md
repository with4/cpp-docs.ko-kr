---
title: _rotl8, _rotl16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _rotl8
- _rotl16
dev_langs:
- C++
helpviewer_keywords:
- _rotl8 intrinsic
- _rotl16 intrinsic
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48a3cfe51f79f0d6068509a5e42693417524417d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328814"
---
# <a name="rotl8-rotl16"></a>_rotl8, _rotl16
**Microsoft 전용**  
  
 입력 값을 지정된 비트 위치 수만큼 MSB(최상위 비트) 왼쪽으로 회전합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned char _rotl8(   
   unsigned char value,   
   unsigned char shift   
);  
unsigned short _rotl16(   
   unsigned short value,   
   unsigned char shift   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `value`  
 회전할 값입니다.  
  
 [in] `shift`  
 회전할 비트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 순환된 값입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`_rotl8`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotl16`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 왼쪽 시프트 작업과는 달리 왼쪽 회전을 실행할 때는 최대값에 속하는 상위 비트가 최하위 비트 위치로 이동됩니다.  
  
## <a name="example"></a>예제  
  
```  
// rotl.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotl8, _rotl16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,  
               i, _rotl8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",  
            s, nBit, _rotl16(s, nBit));  
}  
```  
  
```Output  
Rotating 0x41 left by 0 bits gives 0x41  
Rotating 0x41 left by 1 bits gives 0x82  
Rotating 0x41 left by 2 bits gives 0x5  
Rotating 0x41 left by 3 bits gives 0xa  
Rotating 0x41 left by 4 bits gives 0x14  
Rotating 0x41 left by 5 bits gives 0x28  
Rotating 0x41 left by 6 bits gives 0x50  
Rotating 0x41 left by 7 bits gives 0xa0  
Rotating unsigned short 0x12 left by 10 bits gives 0x4800  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_rotr8, _rotr16](../intrinsics/rotr8-rotr16.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)