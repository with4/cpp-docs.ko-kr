---
title: _mktemp, _wmktemp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wmktemp
- _mktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs: C++
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ade54aef0413e6db897b00f7bfa2e78c428366a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp
고유한 파일 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_mktemp_s, _wmktemp_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `template`  
 파일 이름 패턴입니다.  
  
## <a name="return-value"></a>반환 값  
 각 함수는 수정된 템플릿에 대한 포인터를 반환합니다. 이 함수는 `NULL`의 형식이 잘못되었거나 지정된 템플릿에서 더 이상 고유한 이름을 만들 수 없는 경우 `template`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_mktemp` 함수는 `template` 인수를 수정하여 고유한 파일 이름을 만듭니다. `_mktemp`는 런타임 시스템에서 최근에 사용 중인 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하면서 자동으로 멀티바이트 문자열 인수를 적절하게 처리합니다. `_wmktemp`는 `_mktemp`의 와이드 문자 버전이고, `_wmktemp`의 인수와 반환 값은 와이드 문자 문자열입니다. `_wmktemp` 및 `_mktemp`는 동일하게 작동합니다. 단, `_wmktemp`는 멀티바이트 문자열을 처리하지 않습니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 `template` 인수에는 양식 `base` *XXXXXX*여기서 `base` 는 사용자가 제공한 새 파일 이름의 일부가 속하며 각 X는에서 제공 하는 문자에 대 한 자리 표시자 `_mktemp`합니다. `template`의 각 자리 표시자 문자는 대문자 X여야 합니다. `_mktemp`는 `base`를 유지하고 첫 번째 후행 X를 영문자로 바꿉니다. `_mktemp`는 다음 후행 X를 5자리 숫자 값으로 바꿉니다. 이 값은 호출 프로세스를 식별하는 고유한 번호 또는 다중 스레드 프로그램의 호출 스레드입니다.  
  
 `_mktemp`에 대한 호출에 성공할 때마다 `template`이 수정됩니다. 동일한 `template` 인수를 사용하는 동일한 프로세스 또는 스레드로부터의 각 후속 호출에서 `_mktemp`는 이전 호출에서 `_mktemp`가 반환한 이름과 일치하는 파일 이름을 검사합니다. 지정된 이름에 대한 파일이 없는 경우 `_mktemp`는 해당 이름을 반환합니다. 이전에 반환된 이름에 대한 파일이 존재하는 경우 `_mktemp`는 이전에 반환된 이름에서 사용한 영문자를 다음에 사용할 수 있는 소문자('a'에서 'z'로의 순서)로 대체하여 새 이름을 만듭니다. 예를 들어 `base`가 다음과 같고  
  
```  
fn  
```  
  
 `_mktemp`에서 제공하는 5자리 숫자 값이 12345인 경우 첫 번째 반환된 이름은 다음과 같습니다.  
  
```  
fna12345  
```  
  
 이 이름이 FNA12345 파일을 만드는 데 사용되고 이 파일이 계속 존재하는 경우 `base`에 대해 동일한 `template`를 사용하여 동일한 프로세스 또는 스레드로부터의 호출에서 반환된 다음 이름은 아래와 같습니다.  
  
```  
fnb12345  
```  
  
 FNA12345가 존재하지 않는 경우 반환된 다음 이름은 다시 아래와 같습니다.  
  
```  
fna12345  
```  
  
 `_mktemp`는 기본 및 템플릿 값의 지정된 조합에 대해 최대 26개의 고유한 파일 이름을 만들 수 있습니다. 따라서 FNZ12345는 `_mktemp`가 이 예제에서 사용된 `base` 및 `template` 값에 대해 만들 수 있는 마지막 고유한 파일 이름입니다.  
  
 오류 시 `errno`가 설정됩니다. `template`의 형식이 잘못된 경우(예: X의 개수가 6개보다 적은 경우) `errno`가 `EINVAL`로 설정됩니다. 사용 가능한 파일 이름 26개 모두 이미 존재하기 때문에 `_mktemp`에서 고유한 이름을 만들 수 없는 경우 `_mktemp`는 템플릿을 빈 문자열로 설정하고 `EEXIST`를 반환합니다.  
  
 C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_mktemp`|\<io.h>|  
|`_wmktemp`|\<io.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
```Output  
Unique filename is fna03912  
Unique filename is fnb03912  
Unique filename is fnc03912  
Unique filename is fnd03912  
Unique filename is fne03912  
Unique filename is fnf03912  
Unique filename is fng03912  
Unique filename is fnh03912  
Unique filename is fni03912  
Unique filename is fnj03912  
Unique filename is fnk03912  
Unique filename is fnl03912  
Unique filename is fnm03912  
Unique filename is fnn03912  
Unique filename is fno03912  
Unique filename is fnp03912  
Unique filename is fnq03912  
Unique filename is fnr03912  
Unique filename is fns03912  
Unique filename is fnt03912  
Unique filename is fnu03912  
Unique filename is fnv03912  
Unique filename is fnw03912  
Unique filename is fnx03912  
Unique filename is fny03912  
Unique filename is fnz03912  
Problem creating the template.  
Out of unique filenames.  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)