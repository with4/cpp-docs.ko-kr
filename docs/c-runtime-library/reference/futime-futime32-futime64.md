---
title: "_futime, _futime32, _futime64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _futime64
- _futime32
- _futime
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
- futime
- _futime
- futime64
- _futime64
dev_langs: C++
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 03eda993cbc087d5dc39f2c9d0f985ac5db48099
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="futime-futime32-futime64"></a>_futime, _futime32, _futime64
열린 파일의 수정 시간을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 열린 파일에 대한 파일 설명자입니다.  
  
 `filetime`  
 새 수정 날짜를 포함하는 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 0을 반환합니다. 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 함수 실행을 계속 허용 된,-1을 반환 하 고 `errno` 로 설정 된 `EBADF`, 된 잘못 된 파일 설명자를 나타내는 또는 `EINVAL`, 잘못 된 매개 변수를 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 `_futime` 와 관련 된 열려 있는 파일에 액세스 시간 및 수정 날짜를 설정 하는 루틴 `fd`합니다. `_futime`은 해당 인수가 파일 이름 또는 파일 경로가 아닌 열린 파일의 파일 설명자라는 점을 제외하고 [_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)과 동일합니다. `_utimbuf` 구조체에는 새 수정 날짜 및 액세스 시간에 대한 필드가 포함됩니다. 두 필드 모두 유효한 값을 포함합니다. `_utimbuf32` 및 `_utimbuf64`는 각각 32비트 및 64비트 시간 형식을 사용한다는 점을 제외하고 `_utimbuf`와 동일합니다. `_futime` 및 `_utimbuf`는 64비트 시간 형식을 사용하고 `_futime`의 동작은 `_futime64`와 동일합니다. 이전 동작을 강제 적용하려면 `_USE_32BIT_TIME_T`를 정의합니다. 이렇게 하면 `_futime`의 동작이 `_futime32`와 동일하고 `_utimbuf` 구조체에서 32비트 시간 형식이 사용되어 `__utimbuf32`와 동일해집니다.  
  
 `__utimbuf64` 구조체를 사용하는 `_futime64`는 3000년 12월 31일 23:59:59(UTC)까지 파일 날짜를 일고 수정할 수 있습니다. 반면, 파일의 날짜가 2038년 1월 18일 23:59:59(UTC)보다 나중인 경우에는 `_futime32` 호출에 실패합니다. 1970년 1월 1일 자정은 이러한 함수에 대한 날짜 범위의 하한입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|선택적 헤더|  
|--------------|---------------------|---------------------|  
|`_futime`|\<sys/utime.h>|\<errno.h>|  
|`_futime32`|\<sys/utime.h>|\<errno.h>|  
|`_futime64`|\<sys/utime.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## <a name="input-crtfutimecinput"></a>입력: crt_futime.c_input  
  
```  
Arbitrary file contents.  
```  
  
### <a name="sample-output"></a>샘플 출력  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)