---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
dev_langs:
- C++
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 80836179c63da2f62384abd07fe2a4970d9bce55
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="utime-utime32-utime64-wutime-wutime32-wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
파일 수정 시간을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _utime(  
   const char *filename,  
   struct _utimbuf *times   
);  
int _utime32(  
   const char *filename,  
   struct __utimbuf32 *times   
);  
int _utime64(  
   const char *filename,  
   struct __utimbuf64 *times   
);  
int _wutime(  
   const wchar_t *filename,  
   struct _utimbuf *times   
);  
int _wutime32(  
   const wchar_t *filename,  
   struct __utimbuf32 *times   
);  
int _wutime64(  
   const wchar_t *filename,  
   struct __utimbuf64 *times   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 경로 또는 파일 이름을 포함하는 문자열에 대한 포인터입니다.  
  
 `times`  
 저장된 시간 값에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 파일 수정 시간을 변경한 경우 이러한 각 함수는 0을 반환합니다. 반환 값-1의 오류를 나타냅니다. 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수가 -1을 반환하고 `errno`를 다음 값 중 하나로 설정합니다.  
  
 `EACCES`  
 경로가 디렉터리 또는 읽기 전용 파일을 지정함  
  
 `EINVAL`  
 `times` 인수가 잘못됨  
  
 `EMFILE`  
 파일이 너무 많이 열려 있음(수정 시간을 변경하려면 파일을 열어야 함)  
  
 `ENOENT`  
 경로 또는 파일 이름을 찾을 수 없음  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 변경 날짜가 1970년 1월 1일 자정 이후이고 사용한 함수의 종료 날짜 이전이면 파일의 날짜를 변경할 수 있습니다. `_utime` 및 `_wutime`은 64비트 시간 값을 사용하므로 종료 시간은 3000년 12월 31일 23:59:59(UTC)입니다. `_USE_32BIT_TIME_T`이 이전 동작을 강제 적용하도록 정의된 경우의 종료 날짜는 2038년 1월 18일 23:59:59(UTC)입니다. `_utime32` 또는 `_wutime32`는 `_USE_32BIT_TIME_T` 정의 여부와 관계없이 32비트 시간 형식을 사용하며 항상 종료 날짜가 더 빠릅니다. `_utime64` 또는 `_wutime64`는 항상 64비트 시간 형식을 사용하므로 이러한 함수는 항상 더 이후의 종료 날짜를 지원합니다.  
  
## <a name="remarks"></a>설명  
 `_utime` 함수는 `filename`*으로 지정된 파일의 수정 시간을 설정합니다.* 시간을 변경하려면 프로세스에 파일에 대한 쓰기 권한이 있어야 합니다. Windows 운영 체제에서는 `_utimbuf` 구조체에서 액세스 시간과 수정 시간을 변경할 수 있습니다. `times`가 `NULL` 포인터이면 수정 시간은 현재 현지 시간으로 설정됩니다. 그렇지 않으면 `times`는 SYS\UTIME.H에 정의된 `_utimbuf` 형식의 구조체를 가리켜야 합니다.  
  
 `_utimbuf` 구조체는 `_utime`에서 파일 수정 날짜를 변경하는 데 사용하는 파일 액세스 및 수정 시간을 저장합니다. 이 구조체에는 다음 필드가 포함되어 있습니다. 이 두 필드의 형식은 모두 `time_t`입니다.  
  
 `actime`  
 파일 액세스 시간  
  
 `modtime`  
 파일 수정 시간  
  
 특정 버전의 `_utimbuf` 구조체(`_utimebuf32` 및 `__utimbuf64`)는 32비트 및 64비트 버전의 시간 형식을 사용하여 정의됩니다. 이러한 구조체는 이 함수의 32비트 및 64비트별 버전에서 사용됩니다. `_utimbuf` 자체는 `_USE_32BIT_TIME_T`를 정의하는 경우가 아니면 기본적으로 64비트 시간 형식을 사용합니다.  
  
 `_utime`은 `_utime`의 `filename` 인수가 열린 파일의 파일 설명자가 아닌 파일 이름이나 파일 경로라는 점을 제외하면 `_futime`과 동일합니다.  
  
 `_wutime`은 `_utime`의 와이드 문자 버전이며, `filename`에 대한 `_wutime` 인수는 와이드 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|----------------------|----------------------|  
|`_utime`, `_utime32`, `_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_wutime`|\<utime.h> 또는 \<wchar.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 이 프로그램은 `_utime`을 사용하여 파일 수정 시간을 현재 시간으로 설정합니다.  
  
```  
// crt_utime.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <sys/types.h>  
#include <sys/utime.h>  
#include <time.h>  
  
int main( void )  
{  
   struct tm tma = {0}, tmm = {0};  
   struct _utimbuf ut;  
  
   // Fill out the accessed time structure  
   tma.tm_hour = 12;  
   tma.tm_isdst = 0;  
   tma.tm_mday = 15;  
   tma.tm_min = 0;  
   tma.tm_mon = 0;  
   tma.tm_sec = 0;  
   tma.tm_year = 103;  
  
   // Fill out the modified time structure  
   tmm.tm_hour = 12;  
   tmm.tm_isdst = 0;  
   tmm.tm_mday = 15;  
   tmm.tm_min = 0;  
   tmm.tm_mon = 0;  
   tmm.tm_sec = 0;  
   tmm.tm_year = 102;  
  
   // Convert tm to time_t  
   ut.actime = mktime(&tma);  
   ut.modtime = mktime(&tmm);  
  
   // Show file time before and after  
   system( "dir crt_utime.c" );  
   if( _utime( "crt_utime.c", &ut ) == -1 )  
      perror( "_utime failed\n" );  
   else  
      printf( "File time modified\n" );  
   system( "dir crt_utime.c" );  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/09/2003  05:38 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
File time modified  
 Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/15/2002  12:00 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [_futime, _futime32, _futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_stat, _wstat 함수](../../c-runtime-library/reference/stat-functions.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
