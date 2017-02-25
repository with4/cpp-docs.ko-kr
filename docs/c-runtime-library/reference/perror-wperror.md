---
title: "perror, _wperror | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wperror"
  - "perror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wperror"
  - "_tperror"
  - "perror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tperror 함수"
  - "_wperror 함수"
  - "오류 메시지, 인쇄"
  - "perror 함수"
  - "오류 메시지 인쇄"
  - "tperror 함수"
  - "wperror 함수"
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# perror, _wperror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류 메시지를 인쇄 합니다.  
  
## 구문  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### 매개 변수  
 `string`  
 인쇄할 문자열 메세지 입니다.  
  
## 설명  
 `perror` 함수는 오류 메시지를 `stderr` 에 인쇄합니다.  `_wperror` 는 **\_perror** 의 와이드 문자 버전이고, `string` 인수는 `_wperror`에 대한 와이드 문자 문자열입니다.  그렇지 않으면 `_wperror` 및 **\_perror** 는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string` 는 콜론 뒤에 우선 인쇄되고, 그 다음 오류를 생성한 마지막 라이브러리 호출의 시스템 오류 메세지에 따라 인쇄됩니다. 마지막으로 줄 바꿈 문자입니다.  `string` 가 null 포인터거나 null 문자열에 대한 포인터인 경우, `perror` 는 오류 메세지만 출력합니다.  
  
 오류 번호는 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수에 저장됩니다. \(ERRNO.H에 정의 합니다.H\).  시스템 에러 메시지는 [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 액세스 되는데, 이것은 오류 번호에 따라 정렬된 메시지의 배열입니다.  `perror` 는 `errno` 값을 `_sys_errlist` 에 대한 인덱스 값으로 사용하여 적절할 오류 메세지를 인쇄합니다.  변수 [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 의 값은 `_sys_errlist` 배열 내에서 요소의 최대 수로 정의됩니다.  
  
 정확한 결과에 대해 , 라이브러리 루틴이 오류와 함께 반환하는 즉시 `perror` 를 호출하십시오.  그렇지 않으면, 다음 호출은 `errno` 를 덮어 쓸 수도 있습니다.  
  
 Windows에서 운영 체제에서 ERRNO.H 에 정의된 일부 `errno` 값은 사용되지 않습니다.  이러한 값은 UNIX 운영 체제에 의해 예약 되어 있습니다.  Windows 운영 체제가 사용하는 `errno` 값의 목록에 대해 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  이러한 플랫폼에서 사용하지 않는 `errno` 에 대해 `perror` 는 빈 문자열을 인쇄합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`perror`|\<stdio.h\> or \<stdlib.h\>|  
|`_wperror`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
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
  
## Output  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)