---
title: wcsrtombs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb43cf628abfabe7b5900579ec6995c95c980b2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="wcsrtombss"></a>wcsrtombs_s
와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pReturnValue`  
 변환된 문자 수입니다.  
  
 [out] `mbstr`  
 결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.  
  
 [out] `sizeInBytes`  
 `mbstr` 버퍼의 크기(바이트)입니다.  
  
 [in] `wcstr`  
 변환할 와이드 문자열을 가리킵니다.  
  
 [in] `count`  
 `mbstr` 버퍼에 저장할 최대 바이트 수 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)입니다.  
  
 [in] `mbstate`  
 `mbstate_t` 변환 상태 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공시 0, 실패시 오류 코드.  
  
|오류 조건|반환 값 및 `errno`|  
|---------------------|------------------------------|  
|`mbstr`은 `NULL` 및 `sizeInBytes` > 0입니다.|`EINVAL`|  
|`wcstr`가 `NULL`인 경우|`EINVAL`|  
|대상 버퍼가 너무 작아 변환 문자열을 포함할 수 없습니다(`count`가 `_TRUNCATE`가 아닌 경우 아래 설명 참조).|`ERANGE`|  
  
 이러한 조건 중 하나라도 발생하는 경우, 매개 변수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 발생합니다. 계속해서 실행하도록 허용된 경우 이 함수는 오류 코드를 반환하고 `errno`를 표에 표시된 대로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `wcsrtombs_s` 함수는 `mbstate`에 포함된 변환 상태를 사용하여 `wcstr`이 가리키는 와이드 문자열을 `mbstr`이 가리키는 버퍼에 저장되는 멀티바이트 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.  
  
-   null 와이드 문자가 있는 경우  
  
-   변환할 수 없는 와이드 문자가 있는 경우  
  
-   `mbstr` 버퍼에 저장된 바이트 수가 `count`와 같은 경우  
  
 대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).  
  
 `count`가 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md)이면 `wcsrtombs_s`는 대상 버퍼에 포함할 수 있는 만큼 문자열을 최대한 변환하지만 null 종결자를 포함한 공간은 남겨 둡니다.  
  
 `wcsrtombs_s`는 소스 문자열을 성공적으로 변환하는 경우 `pReturnValue`가 `NULL`이 아니면 null 종결자를 포함하여 변환된 문자열의 크기(바이트)를 `*pReturnValue`에 배치합니다. `mbstr` 인수가 `NULL`이며 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다. `mbstr`이 `NULL`인 경우 `count`가 무시됩니다.  
  
 `wcsrtombs_s`는 멀티바이트 문자로 변환할 수 없는 와이드 문자가 있으면 `*pReturnValue`에 -1을 추가하고, 대상 버퍼를 빈 문자열로 설정하고, `errno`를 `EILSEQ`로 설정한 다음 `EILSEQ`를 반환합니다.  
  
 `wcstr`이 가리키는 시퀀스와 `mbstr`이 가리키는 시퀀스가 겹치는 경우 `wcsrtombs_s`의 동작이 정의되지 않습니다. 현재 로캘의 LC_TYPE 범주가 `wcsrtombs_s`에 영향을 줍니다.  
  
> [!IMPORTANT]
>  `wcstr`와 `mbstr`이 겹치지 않고 `count`가 변환할 와이드 문자 수를 정확하게 반영하도록 합니다.  
  
 `wcsrtombs_s` 함수는 다시 시작할 수 있다는 점에서 [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 `wcstombs_s.` 대신 후속 `wcsrtombs_s` 호출을 사용하는 경우 응용 프로그램은 `wcslen` 대신 `wcsrlen`을 사용해야 합니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="exceptions"></a>예외  
 `wcsrtombs_s` 함수는 이 함수가 실행 중인 동안 현재 스레드의 함수가 `setlocale`을 호출하지 않으며 `mbstate`가 null이면 다중 스레드로부터 안전합니다.  
  
## <a name="example"></a>예  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfully converted.  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)