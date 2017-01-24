---
title: "_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_utime64"
  - "_utime"
  - "_wutime"
  - "_wutime64"
  - "_wutime32"
  - "_utime32"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tutime"
  - "_utime64"
  - "wutime"
  - "utime32"
  - "wutime64"
  - "_utime"
  - "wutime32"
  - "_wutime"
  - "utime"
  - "utime64"
  - "_wutime64"
  - "_utime32"
  - "_tutime64"
  - "_wutime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tutime 함수"
  - "utime32 함수"
  - "utime64 함수"
  - "_utime 함수"
  - "_tutime32 함수"
  - "시간[C++], 파일 수정"
  - "wutime 함수"
  - "_wutime 함수"
  - "_wutime32 함수"
  - "_tutime64 함수"
  - "_tutime 함수"
  - "파일[C++], 수정 시간"
  - "_wutime64 함수"
  - "_utime32 함수"
  - "utime 함수"
  - "_utime64 함수"
  - "wutime64 함수"
  - "wutime32 함수"
  - "tutime64 함수"
  - "tutime32 함수"
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 수정 시간을 설정 합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `filename`  
 경로 및 파일 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `times`  
 저장 된 시간 값에 대 한 포인터입니다.  
  
## 반환 값  
 이러한 각 함수 파일 수정 시간이 변경 된 경우 0을 반환 합니다. 반환 값 –1은 오류를 나타냅니다. 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 잘못 된 매개 변수가 전달 되 면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 되는 경우 이러한 함수가\-1을 반환 하 고 `errno` 는 다음 값 중 하나로 설정 합니다.  
  
 `EACCES`  
 읽기 전용 파일 또는 디렉터리 경로 지정  
  
 `EINVAL`  
 잘못 된 `times` 인수  
  
 `EMFILE`  
 너무 많은 파일이 열려 \(파일은 수정 시간을 변경 하려면 열 수 있어야\)  
  
 `ENOENT`  
 경로 또는 파일 이름을 찾을 수 없습니다.  
  
 참조 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 자세한에 대 한 내용은 이러한 오류 코드 및 기타 반환 코드를 반환 합니다.  
  
 변경 날짜는 1970 년 1 월 1 일 자정 후와 사용 된 함수는 종료 날짜 이전 하는 경우 파일에 대 한 날짜를 변경할 수 있습니다.`_utime` 및 `_wutime` 종료 날짜는 23시 59분: 59, 3000 년 12 월 31 일 UTC에 64 비트 시간 값을 사용 합니다. 경우 `_USE_32BIT_TIME_T` 정의 된 기존 동작을 강제로 종료 날짜는 23시 59분: 59 2038 년 1 월 18 일 UTC입니다.`_utime32` 또는 `_wutime32` 여부에 관계 없이 32 비트 시간 형식을 사용 하 여 `_USE_32BIT_TIME_T` 정의 되 고 항상 이전 종료 날짜입니다.`_utime64` 또는 `_wutime64` 이러한 함수는 항상 이후 종료 날짜를 지원 하므로 항상 64 비트 시간 형식을 그대로 사용 합니다.  
  
## 설명  
 `_utime` 함수를 설정 하 여 지정 된 파일의 수정 시간과 `filename`*.* 프로세스 시간을 변경 하기 위해 파일에 대 한 쓰기 액세스를 가져야 합니다. Windows 운영 체제에서 액세스 시간과 수정 시간에 변경할 수 있습니다는 `_utimbuf` 구조입니다. 경우 `times` 는 `NULL` 포인터의 수정 시간이 현재 현지 시간으로 설정 됩니다. 그렇지 않으면 `times` 형식의 구조체를 가리켜야 `_utimbuf`, SYS\\UTIME에 정의 된 합니다. 8.  
  
 `_utimbuf` 구조에서 사용 하는 파일 액세스 및 수정 시간을 저장 `_utime` 파일 수정 날짜를 변경할 수 있습니다. 구조에는 형식의 모두 다음 필드는 `time_t`:  
  
 `actime`  
 파일 액세스 시간  
  
 `modtime`  
 파일 수정 시간  
  
 특정 버전의는 `_utimbuf` 구조 \(`_utimebuf32` 및 `__utimbuf64`\)는 시간 형식의 32 비트 및 64 비트 버전을 사용 하 여 정의 됩니다. 이러한 32 비트 및 64 비트 특정 버전의이 함수에 사용 됩니다.`_utimbuf` 제외 64 비트 시간 형식을 사용 하 여 기본적으로 자체 `_USE_32BIT_TIME_T` 정의 됩니다.  
  
 `_utime` 동일 `_futime` 점을 제외 하 고는 `filename` 인수의 `_utime` 는 파일 이름 또는 열려 있는 파일의 파일 설명자를 사용 하지 않고는 파일에 대 한 경로입니다.  
  
 `_wutime`은 `_utime`의 와이드 문자 버전이며, `filename`에 대한 `_wutime` 인수는 와이드 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_utime`, `_utime32`, `_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_wutime`|\< utime.h \> 또는 \< wchar.h \>|\<errno.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 프로그램 사용 하 여 `_utime` 파일 수정 시간 현재 시간으로 설정 합니다.  
  
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
  
## 샘플 출력  
  
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
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [\_futime, \_futime32, \_futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)