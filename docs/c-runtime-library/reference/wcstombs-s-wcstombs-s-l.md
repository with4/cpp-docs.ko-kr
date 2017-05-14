---
title: wcstombs_s, _wcstombs_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c407068c475f866062f8973fbacf70fcf6e6cae9
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l
와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pReturnValue`  
 변환된 문자 수입니다.  
  
 [out] `mbstr`  
 결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.  
  
 [in]`sizeInBytes`  
 `mbstr` 버퍼의 크기(바이트)입니다.  
  
 [in] `wcstr`  
 변환할 와이드 문자열을 가리킵니다.  
  
 [in] `count`  
 `mbstr` 버퍼에 저장할 최대 와이드 문자 수이며, 종결 null 문자 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)를 포함하지 않습니다.  
  
 [in] `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 성공시 0, 실패시 오류 코드.  
  
|오류 조건|반환 값 및 `errno`|  
|---------------------|------------------------------|  
|`mbstr`은 `NULL` 및 `sizeInBytes` > 0입니다.|`EINVAL`|  
|`wcstr`가 `NULL`인 경우|`EINVAL`|  
|대상 버퍼가 너무 작아 변환 문자열을 포함할 수 없습니다(`count`가 `_TRUNCATE`가 아닌 경우 아래 설명 참조).|`ERANGE`|  
  
 이러한 조건 중 하나라도 발생하는 경우, 매개 변수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 발생합니다. 계속해서 실행하도록 허용된 경우 이 함수는 오류 코드를 반환하고 `errno`를 표에 표시된 대로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `wcstombs_s` 함수는 `wcstr`가 가리키는 와이드 문자를 `mbstr`가 가리키는 멀티바이트 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.  
  
-   null 와이드 문자가 있는 경우  
  
-   변환할 수 없는 와이드 문자가 있는 경우  
  
-   `mbstr` 버퍼에 저장된 바이트 수가 `count`와 같은 경우  
  
 대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).  
  
 `count`가 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md)이면 `wcstombs_s`는 대상 버퍼에 포함할 수 있는 만큼 문자열을 최대한 변환하지만 null 종결자를 포함한 공간은 남겨 둡니다.  
  
 `wcstombs_s`는 소스 문자열을 성공적으로 변환하는 경우 `pReturnValue`가 `NULL`이 아니면 null 종결자를 포함하여 변환된 문자열의 크기(바이트)를 `*``pReturnValue`에 배치합니다. `mbstr` 인수가 `NULL`이며 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다. `mbstr`이 `NULL`인 경우 `count`가 무시됩니다.  
  
 `wcstombs_s`는 멀티바이트 문자로 변환할 수 없는 와이드 문자가 있으면 `*``pReturnValue`에 0을 추가하고, 대상 버퍼를 빈 문자열로 설정하고, `errno`를 `EILSEQ`로 설정한 다음 `EILSEQ`를 반환합니다.  
  
 `wcstr`이 가리키는 시퀀스와 `mbstr`이 가리키는 시퀀스가 겹치는 경우 `wcstombs_s`의 동작이 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `wcstr`와 `mbstr`이 겹치지 않고 `count`가 변환할 와이드 문자 수를 정확하게 반영하도록 합니다.  
  
 `wcstombs_s`는 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_wcstombs_s_l`은 대신 전달된 로캘을 사용하는 것을 제외하고는 `wcstombs`와 같습니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 이 프로그램은 `wcstombs_s` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 14  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
