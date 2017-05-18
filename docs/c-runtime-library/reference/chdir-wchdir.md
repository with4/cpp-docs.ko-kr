---
title: "_chdir, _wchdir | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wchdir
- _chdir
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
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
dev_langs:
- C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: 22
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
ms.openlocfilehash: 14d6eb678a20d3f3fb0a6250e13005d904aed4b1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="chdir-wchdir"></a>_chdir, _wchdir
현재 작업 디렉터리를 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _chdir(   
   const char *dirname   
);  
int _wchdir(   
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dirname`  
 새 작업 디렉터리의 경로입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 함수는 성공할 경우 0 값을 반환합니다. 반환 값이-1은 오류를 나타냅니다. 지정된 경로를 찾을 수 없는 경우 `errno` 가 `ENOENT`로 설정됩니다. `dirname`이 NULL인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_chdir` 함수는 현재 작업 디렉터리를 `dirname`에 지정된 디렉터리로 변경합니다. `dirname` 매개 변수는 기존 디렉터리를 참조해야 합니다. 이 함수는 모든 드라이브에서 현재 작업 디렉터리를 변경할 수 있습니다. `dirname`에 새 드라이브 문자를 지정하면 기본 드라이브 문자도 변경됩니다. 예를 들어 A가 기본 드라이브 문자이고 \BIN이 현재 작업 디렉터리이면 다음 호출에서 C 드라이브에 대한 현재 작업 디렉터리를 변경하고 C를 새 기본 드라이브로 설정합니다.  
  
```  
_chdir("c:\\temp");  
```  
  
 경로에 선택적 백슬래시 문자(`\`)를 사용하는 경우 단일 백슬래시(`\\`)를 나타내려면 C 문자열 리터럴에 백슬래시 두 개(`\`)를 배치해야 합니다.  
  
 `_wchdir` 은 `_chdir`의 와이드 문자 버전이며, `dirname` 에 대한 `_wchdir` 인수는 와이드 문자 문자열입니다. 그렇지 않을 경우`. _wchdir` 및 `_chdir` 이 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mapping"></a>제네릭 텍스트 루틴 매핑:  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchdir`|`_chdir`|`_chdir`|`_wchdir`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_chdir`|\<direct.h>|\<errno.h>|  
|`_wchdir`|\<direct.h> 또는 \<wchar.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_chdir.c  
// arguments: C:\WINDOWS  
  
/* This program uses the _chdir function to verify  
   that a given directory exists. */  
  
#include <direct.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int argc, char *argv[] )  
{  
  
   if(_chdir( argv[1] ) )  
   {  
      switch (errno)  
      {  
      case ENOENT:  
         printf( "Unable to locate the directory: %s\n", argv[1] );  
         break;  
      case EINVAL:  
         printf( "Invalid buffer.\n");  
         break;  
      default:  
         printf( "Unknown error.\n");  
      }  
   }  
   else  
      system( "dir *.exe");  
}  
```  
  
```Output  
Volume in drive C has no label.  
 Volume Serial Number is 2018-08A1  
  
 Directory of c:\windows  
  
08/29/2002  04:00 AM         1,004,032 explorer.exe  
12/17/2002  04:43 PM            10,752 hh.exe  
03/03/2003  09:24 AM            33,792 ieuninst.exe  
10/29/1998  04:45 PM           306,688 IsUninst.exe  
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE  
03/03/2003  09:24 AM            33,792 Q330994.exe  
08/29/2002  04:00 AM           134,144 regedit.exe  
02/28/2003  06:26 PM            46,352 setdebug.exe  
08/29/2002  04:00 AM            15,360 TASKMAN.EXE  
08/29/2002  04:00 AM            49,680 twunk_16.exe  
08/29/2002  04:00 AM            25,600 twunk_32.exe  
08/29/2002  04:00 AM           256,192 winhelp.exe  
08/29/2002  04:00 AM           266,752 winhlp32.exe  
              13 File(s)      2,249,184 bytes  
               0 Dir(s)  67,326,029,824 bytes free  
```  
  
## <a name="see-also"></a>참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
