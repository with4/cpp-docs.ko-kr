---
title: wcsrtombs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs
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
f1_keywords: wcsrtombs
dev_langs: C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fb18e5f66f431afb86e86815f50217782902b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wcsrtombs"></a>wcsrtombs
와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [wcsrtombs_s](../../c-runtime-library/reference/wcsrtombs-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `mbstr`  
 변환된 결과 멀티바이트 문자열의 주소 위치입니다.  
  
 [in] `wcstr`  
 변환할 와이드 문자열의 위치를 간접적으로 가리킵니다.  
  
 [in] `count`  
 변환할 문자의 수입니다.  
  
 [in] `mbstate`  
 `mbstate_t` 변환 상태 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 변환된 바이트의 수를 반환합니다. null 종결 null 바이트(있는 경우)는 포함되지 않습니다. 오류가 발생하면 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `wcsrtombs` 함수는 `mbstate`에 포함된 지정한 변환 상태부터 시작하여 와이드 문자열을 `wcstr`에서 간접적으로 가리키는 값에서 `mbstr`의 주소로 변환합니다. 이 변환은 null 종결 와이드 문자열이 나오거나, 해당하지 않는 문자가 나오거나, 다음 문자를 변환하면 `count`에 포함된 제한을 초과할 때까지 각 문자에 대해 계속됩니다. `wcsrtombs`는 `count`가 나올 때나 그 전에 와이드 문자 null 문자(L'\0')를 발견하면 해당 문자를 8비트 0으로 변환한 후 실행을 중지합니다.  
  
 따라서 `mbstr`의 멀티바이트 문자열은 `wcsrtombs`가 변환 중에 와이드 문자 null 문자를 발견하는 경우에만 null로 종결됩니다. `wcstr`이 가리키는 시퀀스와 `mbstr`이 가리키는 시퀀스가 겹치는 경우 `wcsrtombs`의 동작이 정의되지 않습니다. 현재 로캘의 LC_TYPE 범주가 `wcsrtombs`에 영향을 줍니다.  
  
 `wcsrtombs` 함수는 다시 시작할 수 있다는 점에서 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어 `wcstombs` 대신 후속 `wcsrtombs` 호출을 사용하는 경우 응용 프로그램은 `wcsnlen` 대신 `wcsrlen`을 사용해야 합니다.  
  
 `mbstr` 인수가 `NULL`이면 `wcsrtombs`는 대상 문자열에 필요한 바이트 크기를 반환합니다. `mbstate`가 null이면 내부 `mbstate_t` 변환 상태가 사용됩니다. 문자 시퀀스 `wchar`에 해당하는 멀티바이트 문자 표현이 없으면 -1이 반환되며 `errno`가 `EILSEQ`로 설정됩니다.  
  
 C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="exceptions"></a>예외  
 `wcsrtombs` 함수는 이 함수가 실행 중인 동안 현재 스레드의 함수가 `setlocale`을 호출하지 않으며 `mbstate`가 null이 아니면 다중 스레드로부터 안전합니다.  
  
## <a name="example"></a>예  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfuly converted.  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)