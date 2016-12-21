---
title: "_futime, _futime32, _futime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_futime64"
  - "_futime32"
  - "_futime"
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
  - "futime"
  - "_futime"
  - "futime64"
  - "_futime64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_futime 함수"
  - "futime32 함수"
  - "futime64 함수"
  - "파일 수정 시간[C++]"
  - "_futime64 함수"
  - "futime 함수"
  - "_futime32 함수"
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _futime, _futime32, _futime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

열려 있는 파일의 수정 시간을 설정합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `fd`  
 열린 파일에 대한 파일 설명자입니다.  
  
 `filetime`  
 새 수정 날짜가 포함된 구조체에 대한 포인터입니다.  
  
## 반환 값  
 성공하면, 0을 반환합니다.  오류가 발생할 때, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로, 잘못된 매개 변수 처리기가 호출됩니다.  만일 실행이 계속되는 경우, 함수는 \-1을 반환하고 `errno` 이 `EBADF`로 설정되고, 잘못된 파일설명자 또는 `EINVAL` 를 나타내거나 잘못된 매개변수를 나타냅니다.  
  
## 설명  
 `_futime` 루틴은 수정한 날짜를 설정하고 `fd`*.* `_futime` 와 연결된 열린 파일에 대한 시간에 접근합니다. 이것은 [\_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) 으로 식별되고 파일에 대한 경로 또는 파일의 이름보다 열린 파일의 파일 식별자를 인수로 하여 제외됩니다.  `_utimbuf` 구조체는 새 변경날짜와 액세스 시간에 대한 필드를 포함합니다.  두가지 필드 모두 올바른 값을 포함해야 합니다.  `_utimbuf32` 와 `_utimbuf64` 는 각각 32비트와 64비트 시간형식들에 대한 `_utimbuf` 예외로 식별됩니다.  `_futime` 와 `_utimbuf` 는 64비트 형식을 사용하고 `_futime` 는 `_futime64` 로 동작함으로써 식별됩니다.  만일 이전 버전의 동작을 적용해야 하는 경우, `_USE_32BIT_TIME_T` 을 정의합니다.  32비트 시간 형식을 하용하기 위해 `_utimbuf` 구조체를 이용하고 `__utimbuf32` 로 이것을 동일하게 만들기 위해, `_futime32` 로 동작하는 것을 식별하기 위해 `_futime` 을 실행합니다.  
  
 `_futime64` 는 `__utimbuf64` 를 사용하는데, UTC 3000년 12월 31일 23시 59시 59분까지 파일 데이터를 읽고 변경할 수 있습니다; 반면 UTC 2038년 1월 18일 19시 14분 7초 이후 `_futime32` 를 호출하여 파일의 데이터를 사용한다면, 실패하게 됩니다.  1970년 1월 1일 자정은 이러한 함수의 날짜 범위의 하한 값입니다.  
  
## 요구 사항  
  
|Function|필수 헤더|선택적 헤더|  
|--------------|-----------|------------|  
|`_futime`|\<sys\/utime.h\>|\<\<errno.h\>\>|  
|`_futime32`|\<sys\/utime.h\>|\<\<errno.h\>\>|  
|`_futime64`|\<sys\/utime.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
## 입력: crt\_futime.c\_input  
  
```  
Arbitrary file contents.  
```  
  
### 샘플 출력  
  
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
  
## 해당 .NET Framework 항목  
  
-   [System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx)  
  
-   [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx)  
  
-   [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)