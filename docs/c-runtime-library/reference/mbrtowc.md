---
title: "mbrtowc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f3446132532fbf212294c0176b697359572b235
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="mbrtowc"></a>mbrtowc
현재 로캘의 멀티바이트 문자를 해당하는 와이드 문자로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t mbrtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   mbstate_t *mbstate  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wchar`  
 변환된 와이드 문자열(`wchar_t` 형식)을 받을 와이드 문자의 주소입니다. 반환 와이드 문자가 필요하지 않으면 이 값은 null 포인터일 수 있습니다.  
  
 `mbchar`  
 바이트 시퀀스(멀티바이트 문자)의 주소입니다.  
  
 `count`  
 검사할 바이트 수입니다.  
  
 `mbstate`  
 변환 상태 개체에 대한 포인터입니다. 이 값이 null 포인터이면 함수는 정적 내부 변환 상태 개체를 사용합니다. 내부 `mbstate_t` 개체는 스레드로부터 안전하지 않으므로 항상 고유한 `mbstate` 인수를 전달하는 것이 좋습니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
 0  
 다음 `count`개 이하의 바이트가 null 와이드 문자(`wchar`이 null 포인터가 아니면 `wchar`에 저장됨)를 나타내는 멀티바이트 문자를 완성합니다.  
  
 1~`count`(포괄)  
 다음 `count`개 이하의 바이트가 올바른 멀티바이트 문자를 완성합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다. `wchar`이 null 포인터가 아니면 해당하는 와이드 문자는 `wchar`에 저장됩니다.  
  
 (size_t)(-1)  
 인코딩 오류가 발생했습니다. 다음 `count`개 이하의 바이트가 완전하며 올바른 멀티바이트 문자에 포함되지 않습니다. 이 경우 `errno`는 EILSEQ로 설정되며 `mbstate`에서 변환 이동 상태가 지정되지 않습니다.  
  
 (size_t)(-2)  
 다음 `count` 바이트가 불완전하지만 올바를 가능성이 있는 멀티바이트 문자에 포함되며 `count`개 바이트가 모두 처리되었습니다. `wchar`에는 값이 저장되지 않지만 `mbstate`는 업데이트되므로 함수가 다시 시작됩니다.  
  
## <a name="remarks"></a>설명  
 `mbchar`이 null 포인터이면 함수는 다음 호출과 같습니다.  
  
 `mbrtowc(NULL, "", 1, &mbstate)`  
  
 이 경우 인수 `wchar` 및 `count`의 값은 무시됩니다.  
  
 `mbchar`이 null 포인터가 아니면 함수는 `count`에서 `mbchar`개 바이트를 검사하여 다음 멀티바이트 문자를 완성하는 데 필요한 바이트 수를 결정합니다. 다음 문자가 올바르면 해당하는 멀티바이트 문자는 null 포인터가 아닌 경우 `wchar`에 저장됩니다. 문자가 해당하는 와이드 null 문자이면 `mbstate`의 결과 상태는 초기 변환 상태가 됩니다.  
  
 `mbrtowc` 함수는 다시 시작할 수 있다는 점에서 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어 `wcsrlen` 대신 후속 `wcslen` 호출을 사용하는 경우 응용 프로그램은 `wcsrtombs` 대신 `wcstombs`을 사용해야 합니다.  
  
## <a name="example"></a>예  
 멀티바이트 문자를 해당하는 와이드 문자로 변환합니다.  
  
```  
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
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Locale set to: "French_Canada.1252"  
Conversion succeeded!  
Multibyte String: AaBbCcÜïα∩≡xXyYzZ  
WC String: AaBbCcÜïα∩≡xXyYzZ  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`mbrtowc`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)