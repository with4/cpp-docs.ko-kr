---
title: "_dupenv_s, _wdupenv_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
dev_langs:
- C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: 16
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3332c33e2d2b79106cf88f143fe99cb91bbce670
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s
현재 환경에서 값을 가져옵니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _dupenv_s(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname  
);  
errno_t _wdupenv_s(  
   wchar_t **buffer,  
   size_t *numberOfElements,  
   const wchar_t *varname  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 변수 값을 저장하는 버퍼입니다.  
  
 `numberOfElements`  
 
          `buffer`의 크기입니다.  
  
 `varname`  
 환경 변수 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 0, 실패 시 오류 코드가 나타납니다.  
  
 이러한 함수는 자신의 매개 변수에 대한 유효성을 검사합니다. 그러나 `buffer` 또는 `varname`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
 충분한 메모리를 할당할 수 없는 경우 이러한 함수는 `buffer`를 `NULL`로 설정하고 `numberOfElements`를 0으로 설정한 다음 `ENOMEM`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_dupenv_s` 함수는 `varname`애 대한 환경 변수 목록을 검색합니다. 변수가 있는 경우 `_dupenv_s`는 버퍼를 할당하고 변수 값을 버퍼로 복사합니다. 버퍼의 주소 및 길이가 `buffer` 및 `numberOfElements`에서 반환됩니다. 버퍼 자체를 할당하여 `_dupenv_s`는 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)에 대한 더욱 편리한 대안을 제공합니다.  
  
> [!NOTE]
>  [free](../../c-runtime-library/reference/free.md)를 호출하여 메모리를 확보하는 것은 호출하는 프로그램이 해야 할 일입니다.  
  
 변수가 없는 경우 이 상황이 오류 조건으로 간주되는 것은 아니기 때문에 `buffer`는 `NULL`로 설정되고 `numberOfElements`는 0으로 설정되며 반환 값은 0입니다.  
  
 버퍼 크기에 관심이 없는 경우에는 `NULL`에 대해 `numberOfElements`을 전달할 수 있습니다.  
  
 `_dupenv_s`는 Windows 운영 체제에서 대/소문자를 구분하지 않습니다. `_dupenv_s`는 전역 변수 `_environ`이 가리키는 환경의 복사본을 사용하여 환경에 액세스합니다. `_environ`에 대한 자세한 내용은 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)의 설명을 참조하세요.  
  
 `buffer`의 값은 환경 변수 값의 복사본입니다. 이 값을 수정하더라도 환경에 영향을 미치지 않습니다. [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md) 함수를 사용하여 환경 변수 값을 수정합니다.  
  
 `_wdupenv_s`는 `_dupenv_s`의 와이드 문자 버전이며, `_wdupenv_s`의 인수는 와이드 문자열입니다. `_wenviron` 전역 변수는 `_environ`의 와이드 문자 버전입니다. `_wenviron`에 대한 자세한 내용은 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)의 설명을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tdupenv_s`|`_dupenv_s`|`_dupenv_s`|`_wdupenv_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_dupenv_s`|\<stdlib.h>|  
|`_wdupenv_s`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_dupenv_s.c  
#include  <stdlib.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [환경 상수](../../c-runtime-library/environmental-constants.md)   
 [_dupenv_s_dbg, _wdupenv_s_dbg](../../c-runtime-library/reference/dupenv-s-dbg-wdupenv-s-dbg.md)   
 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)
