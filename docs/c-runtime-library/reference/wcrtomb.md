---
title: wcrtomb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb
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
f1_keywords: wcrtomb
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c9dfe3b112754d573226fe992d346d57de56406
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtomb"></a>wcrtomb
와이드 문자를 멀티바이트 문자 표현으로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `mbchar`  
 멀티바이트로 변환된 결과 문자입니다.  
  
 [in] `wchar`  
 변환할 와이드 문자입니다.  
  
 [in] `mbstate`  
 `mbstate_t` 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 변환된 멀티바이트 문자를 표시하는 데 필요한 바이트 수를 반환하고, 오류가 발생하면 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `wcrtomb` 함수는 `mbstate`에 포함된 지정한 변환 상태부터 시작하여 와이드 문자를 `wchar`에 포함된 값에서 `mbchar`로 표시되는 주소로 변환합니다. 반환 값은 해당 멀티바이트 문자를 표시하는 데 필요한 바이트 수이지만 `MB_CUR_MAX`바이트까지만 반환됩니다.  
  
 `mbstate`가 null이면 `mbchar`의 변환 상태를 포함하는 내부 `mbstate_t` 개체가 사용됩니다. 문자 시퀀스 `wchar`에 해당하는 멀티바이트 문자 표현이 없으면 -1이 반환되며 `errno`가 `EILSEQ`로 설정됩니다.  
  
 `wcrtomb` 함수는 다시 시작할 수 있다는 점에서 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 `wcstombs` 대신 후속 `wcsrtombs` 호출을 사용하는 경우 응용 프로그램은 `wcsnlen` 대신 `wcsrlen`을 사용해야 합니다.  
  
 C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="exceptions"></a>예외  
 `wcrtomb` 함수는 이 함수가 실행 중인 동안 현재 스레드의 함수가 `setlocale`을 호출하지 않으며 `mbstate`가 null이면 다중 스레드로부터 안전합니다.  
  
## <a name="example"></a>예  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)