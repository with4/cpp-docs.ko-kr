---
title: "_chmod, _wchmod | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chmod"
  - "_wchmod"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_chmod"
  - "_wchmod"
  - "wchmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chmod 함수"
  - "_wchmod 함수"
  - "chmod 함수"
  - "파일 사용 권한[C++]"
  - "파일[C++], 권한 변경"
  - "wchmod 함수"
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _chmod, _wchmod
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 권한 설정을 변경합니다.  
  
## 구문  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### 매개 변수  
 `filename`  
 기존 파일의 이름입니다.  
  
 `pmode`  
 파일의 권한을 설정합니다.  
  
## 반환 값  
 이들 함수는 권한 설정이 성공적으로 변경되었을 경우 0을 반환합니다.  반환 값 \-1은 실패를 나타냅니다.  지정된 파일을 찾을 수 없다면, `errno`가 `ENOENT`로 설정됩니다. 만약 매개 변수가 유효하지 않다면, `errno`이 `EINVAL`로 설정됩니다.  
  
## 설명  
 `_chmod` 함수는 `filename`에 의해서 지정된 파일의 권한 설정을 변경합니다. 권한 설정은 파일 읽기 및 쓰기 권한을 제어합니다.  정수 표현 `pmode`은 SYS\\Stat.h에 정의된 다음의 매니페스트 상수 중 하나 또는 둘 이상을 포함합니다.  
  
 `_S_IWRITE`  
 쓰기에 사용할 수 있습니다.  
  
 `_S_IREAD`  
 읽기에 사용할 수 있습니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기에 사용할 수 있습니다.  
  
 두 상수가 주어지면, 그들은 비트 `OR` 연산자와 결합됩니다.          `|` \).  쓰기 권한이 없는 경우, 읽기 전용 파일입니다.  모든 파일은 항상 읽을 수 있고 쓰기 전용 권한을 부여하는 것은 불가능하다는 것을 주의하세요.  그러므로, `_S_IWRITE` 및 `_S_IREAD | _S_IWRITE` 모드는 동일합니다.  
  
 `_wchmod`는 `_chmod`의 와이드 문자 버전이며, `_wchmod`의 `filename` 인수는 와이드 문자 문자열입니다.  `_wchmod` 및 `_chmod` 는 동일하게 작동합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  경우 `pmode` 매니페스트 상수 중 하나를 조합해 없거나 다른 집합을 포함, 상수 함수 단순히 무시 된.  `filename`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속 실행하는 것이 허용된 경우, `errno`는 `EINVAL` 로 설정되고 함수는 \-1을 반환합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_chmod`|\<io.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
|`_wchmod`|\<io.h\> or \<wchar.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
  **`텍스트의 줄` `텍스트의 줄`읽기 전용으로 모드 설정**  
**액세스가 거부되었습니다.**  
**Mode set to read\/write**   
## 해당 .NET Framework 항목  
  
-   [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
-   [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)