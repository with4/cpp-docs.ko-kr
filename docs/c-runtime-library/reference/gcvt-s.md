---
title: "_gcvt_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _gcvt_s
- gcvt_s
dev_langs: C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a028431bb324fe634ee30ae81eec6c2d3371441
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="gcvts"></a>_gcvt_s
부동 소수점 값을 문자열로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_gcvt](../../c-runtime-library/reference/gcvt.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `buffer`  
 변환 결과를 저장할 버퍼입니다.  
  
 [in] `sizeInBytes`  
 버퍼의 크기입니다.  
  
 [in] `value`  
 변환할 값입니다.  
  
 [in] `digits`  
 저장된 유효 자릿수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 0입니다. 잘못된 매개 변수로 인해 실패할 경우(잘못된 값은 다음 표 참조) [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 실행하도록 허용된 경우 오류 코드가 반환됩니다. 오류 코드는 Errno.h에서 정의됩니다. 이러한 오류 목록은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|반환|`buffer`의 값|  
|--------------|-------------------|-------------|--------------|------------|-----------------------|  
|`NULL`|any|any|any|`EINVAL`|수정되지 않습니다.|  
|`NULL` 아님(유효한 메모리를 가리킴)|0|any|any|`EINVAL`|수정되지 않습니다.|  
|`NULL` 아님(유효한 메모리를 가리킴)|any|any|>= `sizeInBytes`|`EINVAL`|수정되지 않습니다.|  
  
 **보안 문제**  
  
 `buffer`가 유효한 메모리를 가리키지 않고 `NULL`이 아닐 경우 `_gcvt_s`가 액세스 위반을 생성할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `_gcvt_s` 함수는 부동 소수점 `value`를 문자열(소수점 및 가능한 부호 바이트를 포함함)로 변환하고 문자열을 `buffer`에 저장합니다. `buffer`는 변환된 값과 자동으로 추가되는 null 종결 문자를 포함할 만큼 충분히 커야 합니다. 모든 부동 소수점 값에는 `_CVTBUFSIZE` 길이의 버퍼로 충분합니다. `digits` + 1의 버퍼 크기를 사용할 경우 함수는 버퍼 끝을 덮어쓰므로 이 작업에 충분한 버퍼를 제공해야 합니다. `_gcvt_s`는 `digits` 숫자를 10진수 형식으로 생성하려고 합니다. 생성할 수 없는 경우 `digits` 숫자를 지수 형식으로 생성합니다. 변환 시 뒤에 오는 0을 표시하지 않을 수 있습니다.  
  
 C++에서는 템플릿 오버로드로 인해 이 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
 이 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_gcvt_s`|\<stdlib.h>|\<error.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 1.2  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)