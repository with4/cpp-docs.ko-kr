---
title: perror, _wperror | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wperror
- perror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wperror
- _tperror
- perror
dev_langs: C++
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb8dc68154c9a1302fe69dd8416309bf377bdd3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="perror-wperror"></a>perror, _wperror
오류 메시지를 인쇄합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `string`  
 인쇄할 문자열 메시지입니다.  
  
## <a name="remarks"></a>설명  
 `perror` 함수는 오류 메시지를 `stderr`에 인쇄합니다. `_wperror`는 **_perror**의 와이드 문자 버전이고 `_wperror`에 대한 `string` 인수는 와이드 문자열입니다. 그렇지 않으면 `_wperror` 및 **_perror**가 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string`이 먼저 인쇄되고, 뒤에 콜론, 오류를 생성한 마지막 라이브러리 호출에 대한 시스템 오류 메시지, 줄 바꿈 문자가 차례로 인쇄됩니다. `string`이 null 포인터 또는 null 문자열에 대한 포인터인 경우 `perror`만 시스템 오류 메시지를 인쇄합니다.  
  
 오류 번호는 ERRNO.H에 정의되어 있는 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수에 저장됩니다. [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 시스템 오류 메시지에 액세스합니다. 이 변수는 오류 번호순으로 정렬된 메시지 배열입니다. `perror`는 `errno` 값을 `_sys_errlist`에 대한 인덱스로 사용하여 적합한 오류 메시지를 인쇄합니다. [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수의 값은 `_sys_errlist` 배열에 있는 요소의 최대 수로 정의됩니다.  
  
 정확한 결과를 위해 라이브러리 루틴이 오류와 함께 반환되는 즉시 `perror`를 호출합니다. 그렇지 않으면 후속 호출에서 `errno` 값을 덮어쓸 수 있습니다.  
  
 Windows 운영 체제에서 ERRNO.H에 나열된 일부 `errno` 값이 사용되지 않습니다. 이러한 값은 UNIX 운영 체제에서 사용되도록 예약되어 있습니다. Windows 운영 체제에서 사용하는 `errno` 값 목록은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요. `perror`는 이러한 플랫폼에서 사용하지 않는 모든 `errno` 값에 대한 빈 문자열을 인쇄합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`perror`|\<stdio.h> 또는 \<stdlib.h>|  
|`_wperror`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예  
  
```  
// crt_perror.c  
// compile with: /W3  
/* This program attempts to open a file named  
 * NOSUCHF.ILE. Because this file probably doesn't exist,  
 * an error message is displayed. The same message is  
 * created using perror, strerror, and _strerror.  
 */  
  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh;  
  
   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )  
   {  
      /* Three ways to create error message: */  
      perror( "perror says open failed" );  
      printf( "strerror says open failed: %s\n",  
         strerror( errno ) ); // C4996  
      printf( _strerror( "_strerror says open failed" ) ); // C4996  
      // Note: strerror and _strerror are deprecated; consider  
      // using strerror_s and _strerror_s instead.  
   }  
   else  
   {  
      printf( "open succeeded on input file\n" );  
      _close( fh );  
   }  
}  
```  
  
## <a name="output"></a>출력  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)