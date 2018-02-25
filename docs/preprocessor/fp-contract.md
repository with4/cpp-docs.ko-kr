---
title: fp_contract | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7283fa9d9dfb8e35bf96e76d88eb1a9ee80e510
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="fpcontract"></a>fp_contract
부동 소수점 축약 발생 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma fp_contract [ON | OFF]  
```  
  
## <a name="remarks"></a>설명  
 `fp_contract`는 기본적으로 사용하도록 설정되어 있습니다.  
  
 부동 소수점 동작에 대 한 자세한 내용은 참조 하십시오. [/fp (부동 소수점 동작 지정)](../build/reference/fp-specify-floating-point-behavior.md)합니다.  
  
 다른 부동 소수점 pragma는 다음과 같습니다.  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [float_control](../preprocessor/float-control.md)  
  
## <a name="example"></a>예  
 이 샘플에서 생성 된 코드는 Fused Multiply Add를 사용 하지 않습니다 (**fma**) Itanium 프로세서에 명령 합니다. 주석으로 처리 하는 경우 `#pragma fp_contract (off)`, 생성 된 코드에서 사용할는 **fma** 명령입니다.  
  
```  
// pragma_directive_fp_contract.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>  
  
#pragma fp_contract (off)   
  
int main() {  
   double z, b, t;  
  
   for (int i = 0; i < 10; i++) {  
      b = i * 5.5;  
      t = i * 56.025;  
      _set_controlfp(_PC_24, _MCW_PC);  
  
      z = t * i + b;  
      printf_s ("out=%.15e\n", z);  
   }  
}  
```  
  
```Output  
out=0.000000000000000e+000  
out=6.152500152587891e+001  
out=2.351000061035156e+002  
out=5.207249755859375e+002  
out=9.184000244140625e+002  
out=1.428125000000000e+003  
out=2.049899902343750e+003  
out=2.783724853515625e+003  
out=3.629600097656250e+003  
out=4.587524902343750e+003  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)