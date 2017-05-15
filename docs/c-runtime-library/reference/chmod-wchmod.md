---
title: "_chmod, _wchmod | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chmod
- _wchmod
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
- _chmod
- _wchmod
- wchmod
dev_langs:
- C++
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: c0db1569ea6a90892b7eb3d0d8f08f3c9fcf7115
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="chmod-wchmod"></a>_chmod, _wchmod
파일 권한 설정을 변경합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 기존 파일의 이름입니다.  
  
 `pmode`  
 파일에 대한 권한 설정입니다.  
  
## <a name="return-value"></a>반환 값  
 권한 설정을 성공적으로 변경한 경우 이러한 함수는 0을 반환합니다. 반환 값이-1은 오류를 나타냅니다. 지정된 파일을 찾을 수 없는 경우 `errno`는 `ENOENT`로 설정되며, 매개 변수가 올바르지 않은 경우 `errno`는 `EINVAL`로 설정됩니다.  
  
## <a name="remarks"></a>설명  
 `_chmod` 함수 변경 하 여 지정 된 파일의 사용 권한 설정을 `filename`합니다. 권한 설정은 파일에 대한 읽기 및 쓰기 액세스를 제어합니다. 정수 식 `pmode`에는 SYS\Stat.h에 정의된 다음 매니페스트 상수 중 하나 또는 둘 다가 포함되어 있습니다.  
  
 `_S_IWRITE`  
 쓰기를 허용합니다.  
  
 `_S_IREAD`  
 읽기를 허용합니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기를 허용합니다.  
  
 두 상수를 지정하는 경우 비트 `OR` 연산자(`|`)를 사용하여 결합합니다. 쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. 모든 파일을 항상 읽을 수 있으므로 쓰기 전용 권한을 부여할 수 없습니다. 따라서 `_S_IWRITE` 및 `_S_IREAD | _S_IWRITE` 모드는 동일합니다.  
  
 `_wchmod`은 `_chmod`의 와이드 문자 버전이며, `filename`에 대한 `_wchmod` 인수는 와이드 문자열입니다. 그렇지 않으면 `_wchmod`과 `_chmod`이 동일하게 작동합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `pmode`가 매니페스트 상수 중 하나의 조합이 아니거나 다른 상수 집합을 통합하는 경우 함수가 이들을 모두 간단히 무시합니다. `filename`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 -1을 반환합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_chmod`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wchmod`|\<io.h> 또는 \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
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
  
```Output  
  
A line of text.  
  
```  
  
```Output  
  
      A line of text.Mode set to read-only  
Access is denied.  
Mode set to read/write  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat 함수](../../c-runtime-library/reference/stat-functions.md)
