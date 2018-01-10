---
title: __ull_rshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __ull_rshift
dev_langs: C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0951a930ad5baec5b293aee0fe8e70c0a38a12f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ullrshift"></a>__ull_rshift
**Microsoft 전용**  
  
 x64, 오른쪽에 첫 번째 매개 변수로 지정 된 64 비트 값을 두 번째 매개 변수로 지정 된 비트 수 만큼 이동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `mask`  
 오른쪽으로 이동 하려면 64 비트 정수 값입니다.  
  
 [in] `nBit`  
 모듈로 32, x86 및 x64 64로 나눈 나머지 이동할 비트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 / / 마스크 하 여 이동 된 `nBit` 비트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 두 번째 매개 변수 (x64 63) x86 31 보다 큰 경우 해당 번호는 32 (x64 64) 모듈로 이동할 비트 수를 결정 사용 합니다. `ull` 이름 나타냅니다 `unsigned long long (unsigned __int64)`합니다.  
  
## <a name="example"></a>예  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## <a name="output"></a>출력  
  
```  
1  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)