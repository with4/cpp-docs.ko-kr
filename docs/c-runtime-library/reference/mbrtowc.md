---
title: mbrtowc | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- mbrtowc
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
- mbrtowc
dev_langs:
- C++
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3b567fdbf4cca315efb41e8f331fc2d67830503
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="mbrtowc"></a>mbrtowc

현재 로캘의 멀티바이트 문자를 해당하는 와이드 문자로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다.

## <a name="syntax"></a>구문

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>매개 변수

*wchar*<br/>
변환 된 와이드 문자 문자열을 받을 와이드 문자의 주소 (형식 **wchar_t**). 반환 와이드 문자가 필요하지 않으면 이 값은 null 포인터일 수 있습니다.

*mbchar*<br/>
바이트 시퀀스(멀티바이트 문자)의 주소입니다.

*count*<br/>
검사할 바이트 수입니다.

*mbstate*<br/>
변환 상태 개체에 대한 포인터입니다. 이 값이 null 포인터이면 함수는 정적 내부 변환 상태 개체를 사용합니다. 때문에 내부 **mbstate_t** 개체는 스레드로부터 안전 하지, 전달 하는 항상 고유한 것이 좋습니다 *mbstate* 인수입니다.

## <a name="return-value"></a>반환 값

다음 값 중 하나입니다.

0 다음 *count* 개 이하의 바이트가 null 와이드 문자에 저장 되어 있는 나타내는 멀티 바이트 문자를 완성 *wchar*경우 *wchar* 가 null 포인터가 아닙니다.

1 ~ *count*(포함) 다음 *count* 개 이하의 바이트가 올바른 멀티 바이트 문자를 완성 합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다. 해당 와이드 문자에 저장 된 *wchar*경우 *wchar* 가 null 포인터가 아닙니다.

(size_t) (-1) 인코딩 오류가 발생 했습니다. 다음 *count* 또는 이하의 바이트가 완전 하며 올바른 멀티 바이트 문자에 기여 하지 않습니다. 이 경우 **errno** EILSEQ로 설정 되며에서 변환 이동 상태가 설정 되어 *mbstate* 지정 되지 않았습니다.

(size_t) -(2) 다음 *count* 바이트가 불완전 하지만 올바를 가능성이 있는 멀티 바이트 문자를 지정 하 고 모든 *count* 바이트를 처리 합니다. 값은 *wchar*, 하지만 *mbstate* 함수가 다시 시작 하도록 업데이트 됩니다.

## <a name="remarks"></a>설명

경우 *mbchar* 가 null 포인터는 함수는 호출에 해당:

`mbrtowc(NULL, "", 1, &mbstate)`

이 경우에는 인수 값에 *wchar* 및 *count* 무시 됩니다.

경우 *mbchar* 가 null 포인터가 아닌 함수 검사 *개수* 바이트 *mbchar* 필요한 다음을 완료 하는 데 필요한 바이트 수를 확인 하려면 멀티 바이트 문자입니다. 다음 문자가 올바르면 해당 멀티 바이트 문자에 저장 됩니다 *wchar* 가 null 포인터가 아닌 경우. 문자를 해당 와이드 null 문자의 결과 상태가 *mbstate* 초기 변환 상태입니다.

**mbrtowc** 함수에서와 다른 [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) 다시 시작할 합니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, 응용 프로그램 사용 해야 **wcsrlen** 대신 **wcslen** 후속 호출 하는 경우 **wcsrtombs** 대신 사용 됩니다 **wcstombs**.

## <a name="example"></a>예제

멀티바이트 문자를 해당하는 와이드 문자로 변환합니다.

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
