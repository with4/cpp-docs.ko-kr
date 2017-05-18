---
title: "_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstat32i64
- fstat
- fstat64i32
- _fstat64
- _fstati64
- fstat64
- _fstat32
- fstat32i64
- fstati64
- _fstat
- fstat32
- _fstat64i32
dev_langs:
- C++
helpviewer_keywords:
- _fstat64 function
- fstati64 function
- _fstat64i32 function
- _fstat32i64 function
- _fstat32 function
- file information
- fstat64i32 function
- fstat32 function
- fstat function
- fstat64 function
- _fstat function
- _fstati64 function
- fstat32i64 function
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
caps.latest.revision: 23
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
ms.openlocfilehash: 4bf1e3ad35fb03891f9c861255919752d0403d70
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
열린 파일에 대한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _fstat(   
   int fd,  
   struct _stat *buffer   
);  
int _fstat32(   
   int fd,  
   struct __stat32 *buffer   
);  
int _fstat64(   
   int fd,  
   struct __stat64 *buffer   
);  
int _fstati64(   
   int fd,  
   struct _stati64 *buffer   
);  
int _fstat32i64(   
   int fd,  
   struct _stat32i64 *buffer   
);  
int _fstat64i32(   
   int fd,  
   struct _stat64i32 *buffer   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 열린 파일의 파일 설명자입니다.  
  
 `buffer`  
 결과를 저장할 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 파일 상태 정보를 가져오는 경우 0을 반환합니다. 반환 값-1의 오류를 나타냅니다. 파일이 잘못되었거나 `buffer`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EBADF`(잘못된 파일 설명자인 경우) 또는 `EINVAL`(`buffer`가 `NULL`인 경우)로 설정됩니다.  
  
## <a name="remarks"></a>설명  
 `_fstat` 함수는 `fd`와 연결된 열린 파일에 대한 정보를 가져오고 `buffer`가 가리키는 구조체에 저장합니다. SYS\Stat.h에 정의된 `_stat` 구조체에는 다음 필드가 포함되어 있습니다.  
  
 `st_atime`  
 마지막 파일 액세스 시간입니다.  
  
 `st_ctime`  
 파일 생성 시간입니다.  
  
 `st_dev`  
 장치인 경우 `fd`이고, 그렇지 않으면 0입니다.  
  
 `st_mode`  
 파일 모드 정보의 비트 마스크입니다. `fd`가 장치를 참조할 경우 `_S_IFCHR` 비트가 설정됩니다. `fd`가 일반 파일을 참조할 경우 `_S_IFREG` 비트가 설정됩니다. 파일의 사용 권한 모드에 따라 사용자 읽기/쓰기 비트가 설정됩니다. `_S_IFCHR` 및 기타 상수는 SYS\Stat.h에 정의됩니다.  
  
 `st_mtime`  
 파일의 마지막 수정 시간입니다.  
  
 `st_nlink`  
 NTFS가 아닌 파일 시스템에서 항상 1입니다.  
  
 `st_rdev`  
 장치인 경우 `fd`이고, 그렇지 않으면 0입니다.  
  
 `st_size`  
 파일 크기(바이트)입니다.  
  
 `fd`가 장치를 참조할 경우 `st_atime`, `st_ctime`, `st_mtime` 및 `st_size` 필드는 의미가 없습니다.  
  
 Stat.h에서는 Types.h에 정의된 [_dev_t](../../c-runtime-library/standard-types.md) 형식을 사용하므로 코드에서 Stat.h 앞에 Types.h를 포함해야 합니다.  
  
 `__stat64` 구조체를 사용하는 `_fstat64`는 3000년 12월 31일 23:59:59(UTC)까지 파일 생성 날짜를 표현할 수 있습니다. 반면, 다른 함수는 2038년 1월 18일 23:59:59(UTC)까지의 날짜만 나타냅니다. 1970년 1월 1일 자정은 이러한 모든 함수에 대한 날짜 범위의 하한입니다.  
  
 이러한 함수의 변형은 32비트 또는 64비트 시간 형식과 32비트 또는 64비트 파일 길이를 지원합니다. 첫 번째 숫자 접미사(`32` 또는 `64`)는 사용된 시간 형식의 크기를 나타내며, 두 번째 접미사( `i32` 또는 `i64`)는 파일 크기가 32비트 정수로 표시되는지 아니면 64비트 정수로 표시되는지를 나타냅니다.  
  
 `_fstat`는 `_fstat64i32`와 동일하며, `struct _stat`는 64비트 시간을 포함합니다. `_USE_32BIT_TIME_T` 가 정의되지 않는 한 그러하며, 이 경우 이전 동작이 적용됩니다. `_fstat` 는 32비트 시간을 사용하고 `struct _stat` 는 32비트 시간을 포함합니다. 이는 `_fstati64`의 경우에도 마찬가지입니다.  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat의 시간 형식 및 파일 길이 형식 변형  
  
|함수|_USE_32BIT_TIME_T 정의 여부|시간 형식|파일 길이 형식|  
|---------------|------------------------------------|---------------|----------------------|  
|`_fstat`|정의되지 않음|64비트|32비트|  
|`_fstat`|정의됨|32비트|32비트|  
|`_fstat32`|매크로 정의의 영향을 받지 않음|32비트|32비트|  
|`_fstat64`|매크로 정의의 영향을 받지 않음|64비트|64비트|  
|`_fstati64`|정의되지 않음|64비트|64비트|  
|`_fstati64`|정의됨|32비트|64비트|  
|`_fstat32i64`|매크로 정의의 영향을 받지 않음|32비트|64비트|  
|`_fstat64i32`|매크로 정의의 영향을 받지 않음|64비트|32비트|  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_fstat`|\<sys/stat.h> 및 \<sys/types.h>|  
|`_fstat32`|\<sys/stat.h> 및 \<sys/types.h>|  
|`_fstat64`|\<sys/stat.h> 및 \<sys/types.h>|  
|`_fstati64`|\<sys/stat.h> 및 \<sys/types.h>|  
|`_fstat32i64`|\<sys/stat.h> 및 \<sys/types.h>|  
|`_fstat64i32`|\<sys/stat.h> 및 \<sys/types.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_fstat.c  
// This program uses _fstat to report  
// the size of a file named F_STAT.OUT.  
  
#include <io.h>  
#include <fcntl.h>  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <errno.h>  
#include <share.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int fd, result;  
   char buffer[] = "A line to output";  
   char timebuf[26];  
   errno_t err;  
  
   _sopen_s( &fd,  
             "f_stat.out",  
             _O_CREAT | _O_WRONLY | _O_TRUNC,  
             _SH_DENYNO,  
             _S_IREAD | _S_IWRITE );  
   if( fd != -1 )  
      _write( fd, buffer, strlen( buffer ) );  
  
   // Get data associated with "fd":   
   result = _fstat( fd, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      if (errno == EBADF)  
        printf( "Bad file descriptor.\n" );  
      else if (errno == EINVAL)  
        printf( "Invalid argument to _fstat.\n" );  
   }  
   else  
   {  
      printf( "File size     : %ld\n", buf.st_size );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid argument to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
   _close( fd );  
}  
```  
  
```Output  
File size     : 16  
Time modified : Wed May 07 15:25:11 2003  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_filelength, _filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [_stat, _wstat 함수](../../c-runtime-library/reference/stat-functions.md)
