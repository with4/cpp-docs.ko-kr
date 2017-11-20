---
title: _mktemp_s, _wmktemp_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mktemp_s
- _wmktemp_s
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
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs: C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d87ba7e23ccc50cb6debbdb91912f1ae3e90ce1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s
고유한 파일 이름을 만듭니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_mktemp, _wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `template`  
 파일 이름 패턴입니다.  
  
 `sizeInChars`  
 `_mktemp_s`에 있는 싱글바이트 문자 및 `_wmktemp_s`에 있는 와이드 문자의 버퍼 크기입니다(null 종결자 포함).  
  
## <a name="return-value"></a>반환 값  
 이 두 함수는 모두 정상적으로 실행되면 0을 반환하고 실행 시 오류가 발생하면 오류 코드를 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`template`|`sizeInChars`|**반환 값**|**템플릿의 새 값**|  
|----------------|-------------------|----------------------|-------------------------------|  
|`NULL`|모두|`EINVAL`|`NULL`|  
|잘못된 형식(올바른 형식은 `Remarks` 섹션 참조)|모두|`EINVAL`|빈 문자열|  
|any|<= X의 수|`EINVAL`|빈 문자열|  
  
 위의 오류 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `errno`는 `EINVAL`로 설정되고 함수는 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_mktemp_s` 함수는 호출 후에 `template` 포인터가 새 파일 이름을 포함하는 문자열을 가리키도록 `template` 인수를 수정하여 고유한 파일 이름을 만듭니다. `_mktemp_s`는 런타임 시스템에서 최근에 사용 중인 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하면서 자동으로 멀티바이트 문자열 인수를 적절하게 처리합니다. `_wmktemp_s`는 `_mktemp_s`의 와이드 문자 버전이며 `_wmktemp_s`의 인수는 와이드 문자열입니다. `_wmktemp_s` 및 `_mktemp_s`는 동일하게 작동합니다. 단, `_wmktemp_s`는 멀티바이트 문자열을 처리하지 않습니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 `template` 인수의 형식은 `baseXXXXXX`입니다. 여기서 `base`는 지정하는 새 파일 이름에 속하며 각 X는 `_mktemp_s`에서 제공하는 문자열에 대한 자리 표시자입니다. `template`의 각 자리 표시자 문자는 대문자 X여야 합니다. `_mktemp_s`는 `base`를 유지하고 첫 번째 후행 X를 영문자로 바꿉니다. `_mktemp_s`는 다음 후행 X를 5자리 숫자 값으로 바꿉니다. 이 값은 호출 프로세스를 식별하는 고유한 번호 또는 다중 스레드 프로그램의 호출 스레드입니다.  
  
 `_mktemp_s`에 대한 호출에 성공할 때마다 `template`이 수정됩니다. 동일한 `template` 인수를 사용하는 동일한 프로세스 또는 스레드로부터의 각 후속 호출에서 `_mktemp_s`는 이전 호출에서 `_mktemp_s`가 반환한 이름과 일치하는 파일 이름을 검사합니다. 지정된 이름에 대한 파일이 없는 경우 `_mktemp_s`는 해당 이름을 반환합니다. 이전에 반환된 이름에 대한 파일이 존재하는 경우 `_mktemp_s`는 이전에 반환된 이름에서 사용한 영문자를 다음에 사용할 수 있는 소문자('a'에서 'z'로의 순서)로 대체하여 새 이름을 만듭니다. 예를 들어 `base`가 다음과 같고  
  
```  
fn  
```  
  
 `_mktemp_s`에서 제공하는 5자리 숫자 값이 12345인 경우 첫 번째 반환된 이름은 다음과 같습니다.  
  
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
  
 `_mktemp_s`는 기본 및 템플릿 값의 지정된 조합에 대해 최대 26개의 고유한 파일 이름을 만들 수 있습니다. 따라서 FNZ12345는 `_mktemp_s`가 이 예제에서 사용된 `base` 및 `template` 값에 대해 만들 수 있는 마지막 고유한 파일 이름입니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h>|  
|`_wmktemp_s`|\<io.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)