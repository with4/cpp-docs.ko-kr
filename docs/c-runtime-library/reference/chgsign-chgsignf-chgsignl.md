---
title: "_chgsign, _chgsignf, _chgsignl | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _chgsignl
- _chgsign
- _chgsignf
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _chgsignf
- chgsign
- _chgsignl
- _chgsign
dev_langs:
- C++
helpviewer_keywords:
- _chgsignl function
- _chgsignf function
- chgsign function
- _chgsign function
ms.assetid: a6646f8e-213d-4564-8617-f43bc66f989f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c5e9a1f7f85e2583a1dc07cb85b6a20535f5c0e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="chgsign-chgsignf-chgsignl"></a>_chgsign, _chgsignf, _chgsignl
부동 소수점 인수의 부호를 반대로 뒤바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```  
double _chgsign(   
   double x   
);  
float _chgsignf(  
   float x   
);  
long double _chgsignl(   
   long double x   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 변경할 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `_chgsign` 함수는 부동 소수점 인수 `x`와 같은 값을 반환하지만, 그 부호는 반대로 합니다. 반환되는 오류가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_chgsign`|\<float.h>|  
|`_chgsignf`, `_chgsignl`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)