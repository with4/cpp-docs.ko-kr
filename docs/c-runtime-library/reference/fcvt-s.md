---
title: "_fcvt_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fcvt_s
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
- fcvt_s
- _fcvt_s
dev_langs: C++
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bd77d18f63885aa29f49ce8bd497f935d292e0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fcvts"></a>_fcvt_s
부동 소수점 숫자를 문자열로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_fcvt](../../c-runtime-library/reference/fcvt.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `buffer`  
 변환 결과를 포함할 제공된 버퍼입니다.  
  
 [in] `sizeInBytes`  
 버퍼 크기(바이트)입니다.  
  
 [in] `value`  
 변환할 숫자입니다.  
  
 [in] `count`  
 소수점 뒤의 자릿수입니다.  
  
 [out] `dec`  
 저장된 소수점 위치의 포인터입니다.  
  
 [out] `sign`  
 저장된 부호 표시기의 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 이러한 오류 목록은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 다음 표에 나와 있는 잘못된 매개 변수의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`buffer`|`sizeInBytes`|값|count|dec|sign|반환|`buffer`의 값|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|수정되지 않습니다.|  
|`NULL` 아님(유효한 메모리를 가리킴)|<=0|any|any|any|any|`EINVAL`|수정되지 않습니다.|  
|any|any|any|any|`NULL`|any|`EINVAL`|수정되지 않습니다.|  
|any|any|any|any|any|`NULL`|`EINVAL`|수정되지 않습니다.|  
  
 **보안 문제**  
  
 `buffer`가 유효한 메모리를 가리키지 않고 `NULL`이 아닐 경우 `_fcvt_s`가 액세스 위반을 생성할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `_fcvt_s` 함수는 부동 소수점 숫자를 null 종료 문자열로 변환합니다. `value` 매개 변수는 변환할 부동 소수점 숫자입니다. `_fcvt_s`는 `value` 중 숫자를 문자열로 저장하고 null 문자('\0')를 추가합니다. `count` 매개 변수는 소수점 뒤에 저장할 자릿수를 지정합니다. 나머지 숫자는 `count`자리로 반올림됩니다. 정밀도의 숫자가 `count`개보다 적으면 문자열이 0으로 채워집니다.  
  
 숫자만 문자열에 저장됩니다. 소수점 위치와 `value`의 부호는 호출 후에 `dec` 및 `sign`에서 얻을 수 있습니다. `dec` 매개 변수는 문자열의 시작을 기준으로 소수점의 위치를 제공하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. 매개 변수 `sign`은 `value`의 부호를 나타내는 정수를 가리킵니다. `value`가 양수일 경우 정수가 0으로 설정되고 `value`가 음수일 경우 0이 아닌 숫자로 설정됩니다.  
  
 모든 부동 소수점 값에는 `_CVTBUFSIZE` 길이의 버퍼로 충분합니다.  
  
 `_ecvt_s`와 `_fcvt_s`의 차이는 `count` 매개 변수의 해석에 있습니다. `_ecvt_s`해석 `count` 으로 출력 문자열에 전체 자릿수 및 `_fcvt_s` 해석 `count` 소수점 뒤에 자릿수의 숫자입니다.  
  
 C++에서는 템플릿 오버로드로 인해 이 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
 이 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|선택적 헤더|  
|--------------|---------------------|---------------------|  
|`_fcvt_s`|\<stdlib.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
 **라이브러리:** 모든 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 120000  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)