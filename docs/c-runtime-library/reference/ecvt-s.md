---
title: "_ecvt_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 81bcb9fe1306f5affa49672269890d6f5888a3ac
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="ecvts"></a>_ecvt_s
`double` 숫자를 문자열로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_ecvt](../../c-runtime-library/reference/ecvt.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `_Buffer`  
 변환의 결과인 숫자 문자열에 대한 포인터로 채워집니다.  
  
 [in] `_SizeInBytes`  
 버퍼의 크기(바이트)입니다.  
  
 [in] `_Value`  
 변환할 숫자입니다.  
  
 [in] `_Count`  
 저장된 자릿수입니다.  
  
 [out] `_Dec`  
 저장된 소수점 위치입니다.  
  
 [out] `_Sign`  
 변환된 숫자의 부호입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 다음 표에 나와 있는 잘못된 매개 변수의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`_Buffer`|`_SizeInBytes`|_Value|_Count|_Dec|_Sign|반환 값|`buffer`의 값|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|  
|`NULL`|모두|모두|모두|모두|모두|`EINVAL`|수정되지 않습니다.|  
|`NULL` 아님(유효한 메모리를 가리킴)|<=0|any|모두|모두|모두|`EINVAL`|수정되지 않습니다.|  
|any|모두|모두|모두|`NULL`|모두|`EINVAL`|수정되지 않습니다.|  
|any|모두|모두|모두|모두|`NULL`|`EINVAL`|수정되지 않습니다.|  
  
 **보안 문제**  
  
 `buffer`가 유효한 메모리를 가리키지 않고 `NULL`이 아닐 경우 `_ecvt_s`가 액세스 위반을 생성할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `_ecvt_s` 함수는 부동 소수점 숫자를 문자열로 변환합니다. `_Value` 매개 변수는 변환할 부동 소수점 숫자입니다. 이 함수는 `_Value` 중 최대 `count`개의 숫자를 문자열로 저장하고 null 문자('\0')를 추가합니다. `_Value`의 숫자 개수가 `_Count`개를 초과하면 낮은 자리 숫자가 반올림됩니다. 숫자가 `count`개보다 적으면 문자열이 0으로 채워집니다.  
  
 숫자만 문자열에 저장됩니다. 소수점 위치와 `_Value`의 부호는 호출 후에 `_Dec` 및 `_Sign`에서 얻을 수 있습니다. `_Dec` 매개 변수는 문자열의 시작을 기준으로 소수점의 위치를 제공하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. `_Sign` 매개 변수는 변환된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.  
  
 모든 부동 소수점 값에는 `_CVTBUFSIZE` 길이의 버퍼로 충분합니다.  
  
 `_ecvt_s`와 `_fcvt_s`의 차이는 `_Count` 매개 변수의 해석에 있습니다. `_ecvt_s`는 `_Count`를 출력 문자열의 전체 숫자 개수로 해석하는 반면, `_fcvt_s`는 `_Count`를 소수점 뒤의 자릿수로 해석합니다.  
  
 C++에서는 템플릿 오버로드로 인해 이 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
 이 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|선택적 헤더|  
|--------------|---------------------|---------------------|  
|`_ecvt_s`|\<stdlib.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 12000  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)
