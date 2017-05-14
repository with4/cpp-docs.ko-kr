---
title: "_creat, _wcreat | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _creat
- _wcreat
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: f034e2b80cc1bd3e7b5fc4578a6f5e77a060593c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="creat-wcreat"></a>_creat, _wcreat
새 파일을 만듭니다. `_creat` 및 `_wcreat`는 더 이상 사용되지 않습니다. 대신 [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md)를 사용하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 새 파일의 이름입니다.  
  
 `pmode`  
 권한 설정  
  
## <a name="return-value"></a>반환 값  
 이러한 함수는 성공하는 경우 생성된 파일에 파일 설명자를 반환합니다. 그렇지 않으면 함수는-1을 반환 하 고 설정 `errno` 다음 표에 나와 있는 것 처럼 합니다.  
  
|`errno` 설정|설명|  
|---------------------|-----------------|  
|`EACCES`|`filename`은 기존의 읽기 전용 파일을 지정하거나 파일 대신 디렉터리를 지정합니다.|  
|`EMFILE`|사용 가능한 추가 파일 설명자가 없습니다.|  
|`ENOENT`|지정된 파일을 찾을 수 없습니다.|  
  
 `filename`이 NULL인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_creat` 함수는 새 파일을 만들거나 기존 파일을 열어 자릅니다. `_wcreat`은 `_creat`의 와이드 문자 버전이며, `filename`에 대한 `_wcreat` 인수는 와이드 문자열입니다. 그렇지 않으면 `_wcreat`과 `_creat`이 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 `filename`으로 지정된 파일이 없으면 지정된 권한 설정으로 새 파일이 생성되고 작성할 수 있도록 열립니다. 파일이 이미 있으며 해당 권한 설정으로 작성할 수 있는 경우 `_creat`는 파일의 길이를 0으로 잘라서 이전 내용을 제거하고, 작성할 수 있도록 파일을 엽니다. 권한 설정 `pmode`는 새로 생성된 파일에만 적용됩니다. 새 파일은 처음으로 닫힌 이후 지정된 권한 설정을 받습니다. 정수 식 `pmode`에는 SYS\Stat.h에 정의된 매니페스트 상수 `_S_IWRITE` 및 `_S_IREAD` 중 하나 또는 둘 다가 포함되어 있습니다. 두 상수가 지정된 경우 비트 `OR` 연산자(**|**)를 사용하여 결합됩니다. `pmode` 매개 변수는 다음 값 중 하나로 설정됩니다.  
  
|값|정의|  
|-----------|----------------|  
|`_S_IWRITE`|쓰기를 허용합니다.|  
|`_S_IREAD`|읽기를 허용합니다.|  
|`_S_IREAD &#124; _S_IWRITE`|읽기 및 쓰기를 허용합니다.|  
  
 쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. 모든 파일을 항상 읽을 수 있으므로 쓰기 전용 권한을 부여할 수 없습니다. 그러면 `_S_IWRITE` 및 `_S_IREAD | _S_IWRITE` 모드는 동일합니다. `_creat`를 사용하여 열린 파일은 항상 `_SH_DENYNO`와 호환 모드로 열립니다([_sopen](../../c-runtime-library/reference/sopen-wsopen.md) 참조).  
  
 권한을 설정하기 전에 `_creat`는 현재 파일 권한 마스크를 `pmode`에 적용합니다([_umask](../../c-runtime-library/reference/umask.md) 참조). `_creat`는 주로 이전 라이브러리와의 호환성을 위해 제공됩니다. `oflag` 매개 변수의 `_O_CREAT` 및 `_O_TRUNC`를 사용한 `_open` 호출은 `_creat`와 동일하며, 새 코드에 적합합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_creat`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wcreat`|\<io.h> 또는 \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
```Output  
Created data file.  
```  
  
## <a name="see-also"></a>참고 항목  
 [하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)
