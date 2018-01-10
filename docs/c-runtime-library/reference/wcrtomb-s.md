---
title: wcrtomb_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb_s
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
f1_keywords: wcrtomb_s
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13134a3e6b34be13d6d878cf94f204bb6c87a458
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtombs"></a>wcrtomb_s
와이드 문자를 멀티바이트 문자 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pReturnValue`  
 기록된 바이트 수를 반환하거나, 오류가 발생하면 -1을 반환합니다.  
  
 [out] `mbchar`  
 멀티바이트로 변환된 결과 문자입니다.  
  
 [in] `sizeOfmbchar`  
 `mbchar` 변수의 크기(바이트)입니다.  
  
 [in] `wchar`  
 변환할 와이드 문자입니다.  
  
 [in] `mbstate`  
 `mbstate_t` 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 0을 반환하거나, 오류가 발생하면 `errno` 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `wcrtomb_s` 함수는 `mbstate`에 포함된 지정한 변환 상태부터 시작하여 와이드 문자를 `wchar`에 포함된 값에서 `mbchar`로 표시되는 주소로 변환합니다. `pReturnValue` 값은 변환된 바이트 수이지만 `MB_CUR_MAX`바이트까지만 반환되며 오류가 발생한 경우에는 -1이 반환됩니다.  
  
 `mbstate`가 null이면 내부 `mbstate_t` 변환 상태가 사용됩니다. `wchar`에 포함된 문자에 해당하는 멀티바이트가 없으면 `pReturnValue`의 값은 -1이 되며 함수는 `errno` 값 `EILSEQ`를 반환합니다.  
  
 `wcrtomb_s` 함수는 다시 시작할 수 있다는 점에서 [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 `wcstombs_s.` 대신 후속 `wcsrtombs_s` 호출을 사용하는 경우 응용 프로그램은 `wcslen` 대신 `wcsrlen`을 사용해야 합니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 간편하게 사용할 수 있습니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="exceptions"></a>예외  
 `wcrtomb_s` 함수는 이 함수가 실행 중인 동안 현재 스레드의 함수가 `setlocale`을 호출하지 않으며 `mbstate`가 null이면 다중 스레드로부터 안전합니다.  
  
## <a name="example"></a>예  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
The corresponding wide character "Q" was converted to a the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)