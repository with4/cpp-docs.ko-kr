---
title: wcstombs_s, _wcstombs_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 863f6dc5b1c7a41145607e8f8ba83466324dac07
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
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

[out] *pReturnValue*  
변환된 문자 수입니다.  
  
[out] *mbstr*  
결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.  
  
[in] *sizeInBytes*  
바이트의 크기는 *mbstr* 버퍼입니다.  
  
[in] *wcstr*  
변환할 와이드 문자열을 가리킵니다.  
  
[in] *count*  
에 저장 하는 바이트의 최대 수는 *mbstr* 버퍼에 null 종결 문자를 제외 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.  
  
[in] *로캘*  
사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  

성공시 0, 실패시 오류 코드.  
  
|오류 조건|반환 값 및 `errno`|  
|---------------------|------------------------------|  
|*mbstr* 은 `NULL` 및 *sizeInBytes* > 0|`EINVAL`|  
|*wcstr* is `NULL`|`EINVAL`|  
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *count* 은 `_TRUNCATE`; 아래 설명 참조)|`ERANGE`|  
  
이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 오류 코드를 반환하고 `errno`를 표에 표시된 대로 설정합니다.  
  
## <a name="remarks"></a>설명  

`wcstombs_s` 함수가 가리키는 와이드 문자 문자열 변환 *wcstr* 가리키는 버퍼에 저장 된 멀티 바이트 문자에 *mbstr*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.  
  
-   null 와이드 문자가 있는 경우  
  
-   변환할 수 없는 와이드 문자가 있는 경우  
  
-   에 저장 된 바이트 수는 *mbstr* equals 버퍼링 *count*합니다.  
  
대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).  
  
경우 *개수* 는 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md), 다음 `wcstombs_s` 만큼 문자열 최대한 변환 하지만 null 종결자를 위한 대상 버퍼에 적합 합니다. 반환 값은 문자열이 잘리는 경우 `STRUNCATE`는 변환이 성공한 것으로 간주 됩니다.  
  
경우 `wcstombs_s` 소스 문자열을 성공적으로 변환에 null 종결자를 포함 하 여 변환된 된 문자열의 바이트에서 크기를 가져가서 `*pReturnValue` (제공 된 *pReturnValue* 않습니다 `NULL`). 이 경우에는 *mbstr* 인수가 `NULL` 이며 필요한 버퍼 크기를 결정 하는 방법을 제공 합니다. 되는 경우 *mbstr* 은 `NULL`, *count* 는 무시 됩니다.  
  
`wcstombs_s`는 멀티바이트 문자로 변환할 수 없는 와이드 문자가 있으면 `*pReturnValue`에 0을 추가하고, 대상 버퍼를 빈 문자열로 설정하고, `errno`를 `EILSEQ`로 설정한 다음 `EILSEQ`를 반환합니다.  
  
시퀀스에서 가리키는 경우 *wcstr* 및 *mbstr* 겹치는 경우의 동작 `wcstombs_s` 정의 되지 않습니다.  
  
> [!IMPORTANT]
>  되도록 *wcstr* 및 *mbstr* 이 겹치지 않을 있는지 *개수* 올바르게 변환할 와이드 문자 수를 반영 합니다.  
  
`wcstombs_s`는 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_wcstombs_s_l`은 대신 전달된 로캘을 사용하는 것을 제외하고는 `wcstombs`와 같습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  

이 프로그램은 `wcstombs_s` 함수의 동작을 보여 줍니다.  
  
```C  
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