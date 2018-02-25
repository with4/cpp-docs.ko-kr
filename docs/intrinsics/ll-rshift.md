---
title: __ll_rshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e404375eefaf456ae22d2eca5cb66a13dd6a72ae
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="llrshift"></a>__ll_rshift
**Microsoft 전용**  
  
 오른쪽에 첫 번째 매개 변수로 지정 된 64 비트 값을 두 번째 매개 변수로 지정 된 비트 수 만큼 이동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `Mask`  
 오른쪽으로 이동 하려면 64 비트 정수 값입니다.  
  
 [in] `nBit`  
 X64, 64로 나눈 나머지 및 x86 32 모듈로 이동할 비트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 / / 마스크 하 여 이동 된 `nBit` 비트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__ll_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 두 번째 매개 변수 64 x64 (x86 32) 보다 큰 경우 해당 개수 계산 된 것 (x86 32) 64로 나눈 나머지 이동할 비트 수를 결정 합니다. `ll` 접두사에는 작업 임을 나타냅니다. `long long`, 다른 이름을 `__int64`, 64 비트 부호 있는 정수 형식입니다.  
  
## <a name="example"></a>예  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## <a name="output"></a>출력  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **참고** 경우 `_ull_rshift` 되었습니다을 사용 하는 오른쪽 이동 된 값의 MSB 있었을 0 되므로 원하는 결과 하지 얻은 음수 값의 경우.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)