---
title: __min | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- __min
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
apitype: DLLExport
f1_keywords:
- __min
- min
- _min
dev_langs:
- C++
helpviewer_keywords:
- __min macro
- min macro
- minimum macro
- _min macro
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8e4f282331caaef9b56d1ca0b52ebf7c5e63ab6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="min"></a>__min
두 값 중 더 작은 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 숫자 데이터 형식입니다.  
  
 `a, b`  
 비교될 숫자 형식의 값입니다.  
  
## <a name="return-value"></a>반환 값  
 두 인수 중 더 작은 값입니다.  
  
## <a name="remarks"></a>설명  
 `__min` 매크로는 두 값을 비교해서 더 작은 값을 반환합니다. 인수는 서명되거나 서명되지 않은 모든 숫자 데이터 형식일 수 있습니다. 두 인수와 반환 값은 동일한 데이터 형식이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`__min`|\<stdlib.h>|  
  
## <a name="example"></a>예  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
```Output  
The larger of 10 and 21 is 21  
The smaller of 10 and 21 is 10  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [__max](../../c-runtime-library/reference/max.md)