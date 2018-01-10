---
title: "mbrlen | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords: mbrlen
dev_langs: C++
helpviewer_keywords: mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58f94a79bb5304ed1ebfe9b7c2241b28497c8c4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mbrlen"></a>mbrlen
현재 로캘에서 멀티바이트 문자열을 완성하는 데 필요한 바이트 수를 결정합니다. 이때 멀티바이트 문자의 중간에서 다시 시작할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t mbrlen(  
   const char * str,  
   size_t count,  
   mbstate_t * mbstate  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `str`  
 멀티바이트 문자열에서 검사할 다음 바이트에 대한 포인터입니다.  
  
 `count`  
 검사할 최대 바이트 수입니다.  
  
 `mbstate`  
 `str` 초기 바이트의 현재 이동 상태에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
 0  
 다음 `count`개 이하의 바이트가 와이드 null 문자를 나타내는 멀티바이트 문자를 완성합니다.  
  
 1~`count`(포괄)  
 다음 `count`개 이하의 바이트가 올바른 멀티바이트 문자를 완성합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다.  
  
 (size_t)(-2)  
 다음 `count` 바이트가 불완전하지만 올바를 가능성이 있는 멀티바이트 문자에 포함되며 `count`개 바이트가 모두 처리되었습니다.  
  
 (size_t)(-1)  
 인코딩 오류가 발생했습니다. 다음 `count`개 이하의 바이트가 완전하며 올바른 멀티바이트 문자에 포함되지 않습니다. 이 경우 `errno`는 EILSEQ로 설정되며 `mbstate`에서 변환 상태가 지정되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `mbrlen` 함수는 `count`이 가리키는 바이트부터 최대 `str`바이트를 검사하여 다음 멀티바이트 문자를 완성하는 데 필요한 바이트 수를 결정합니다(이동 시퀀스 포함). 이러한 방식은 `mbrtowc(NULL, str, count, &mbstate)`를 호출하는 것과 같습니다. 여기서 `mbstate`는 사용자가 제공하는 `mbstate_t` 개체이거나 라이브러리에서 제공되는 정적 내부 개체입니다.  
  
 `mbrlen` 함수는 `mbstate` 매개 변수에서 불완전한 멀티바이트 문자의 이동 상태를 저장하고 사용합니다. 따라서 필요한 경우 `mbrlen`을 멀티바이트 문자 중간에서 다시 시작하여 최대 `count`바이트를 검사할 수 있습니다. `mbstate`가 null 포인터이면 `mbrlen`은 내부 정적 `mbstate_t` 개체를 사용하여 이동 상태를 저장합니다. 내부 `mbstate_t` 개체는 스레드로부터 안전하지 않으므로 항상 고유한 `mbstate` 매개 변수를 할당하고 전달하는 것이 좋습니다.  
  
 `mbrlen` 함수는 다시 시작할 수 있다는 점에서 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 이동 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어 `wcsrlen` 대신 후속 `wcslen` 호출을 사용하는 경우 응용 프로그램은 `wcsrtombs` 대신 `wcstombs.`을 사용해야 합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|적용할 수 없음|적용할 수 없음|`mbrlen`|적용할 수 없음|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`mbrlen`|\<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 이 예제에서는 멀티바이트 문자 해석이 현재 코드 페이지에 따라 달라지는 방식과 `mbrlen`의 다시 시작 기능을 보여 줍니다.  
  
```C  
// crt_mbrlen.c  
// Compile by using: cl crt_mbrlen.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
size_t Example(const char * pStr)  
{  
    size_t      charLen = 0;  
    size_t      charCount = 0;  
    mbstate_t   mbState = {0};  
  
    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&  
            charLen != (size_t)-1)  
    {  
        if (charLen != (size_t)-2) // if complete mbcs char,  
        {  
            charCount++;  
        }  
    }   
    return (charCount);  
}   
  
int main( void )  
{  
    int         cp;  
    size_t      charCount = 0;  
    const char  *pSample =   
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";  
  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
  
    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale  
    _setmbcp(932); // and Japanese multibyte code page  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
}  
```  
  
```Output  
  
Code page: 0  
é╨éτé¬é╚: Shift-jis hiragana.  
Character count: 29  
  
Code page: 932  
????: Shift-jis hiragana.  
Character count: 25  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)