---
title: _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _sprintf_p
- _swprintf_p_l
- _swprintf_p
- _sprintf_p_l
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
- _sprintf_p
- _swprintf_p_l
- _sprintf_p_l
- _swprintf_p
- sprintf_p
- swprint_p_l
- swprintf_p
- swprintf_p_l
dev_langs:
- C++
helpviewer_keywords:
- sprintf_p_l function
- swprintf_p function
- swprintf_p_l function
- _sprintf_p function
- _sprintf_p_l function
- _swprintf_p function
- sprintf_p function
- _stprintf_p function
- stprintf_p function
- _swprintf_p_l function
- stprintf_p_l function
- formatted text [C++]
- _stprintf_p_l function
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46e82b8485458290629916a1eb9f44a2bf2f23ab
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="sprintfp-sprintfpl-swprintfp-swprintfpl"></a>_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
형식 문자열에서 매개 변수가 사용되는 순서를 지정하는 기능과 함께 문자열에 형식이 지정된 데이터를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument_list]  
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument_list]  
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument_list]  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument_list]   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 출력을 위한 저장소 위치  
  
 `sizeOfBuffer`  
 저장할 최대 문자 수입니다.  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument_list`  
 서식 문자열에 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 작성 된 문자 수 또는 오류가 발생 한 경우-1입니다.  
  
## <a name="remarks"></a>설명  
 `_sprintf_p` 함수는 일련의 문자 및 값의 서식을 지정하고 `buffer`에 저장합니다. 각 인수에는 `argument_list` (있는 경우)이 변환 되 고 해당 형식 사양에 따라 출력 `format`합니다. `format` 인수를 사용 하 여 [형식 사양 구문 printf 및 wprintf 함수에 대 한](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다. 기록된 마지막 문자 뒤에 `NULL` 문자가 추가됩니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다. `_sprintf_p`와 `sprintf_s`의 차이점은 `_sprintf_p`에서 위치 매개 변수를 지원한다는 점입니다. 이는 인수가 형식 문자열에서 사용되는 순서를 지정할 수 있습니다. 자세한 내용은 [printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.  
  
 `_swprintf_p`는 `_sprintf_p`의 와이드 문자 버전이며, `_swprintf_p`에 대한 포인터 인수는 와이드 문자 문자열입니다. `_swprintf_p`에서 인코딩 오류의 탐지 방식은 `_sprintf_p`와 다를 수 있습니다. `_swprintf_p`는 `FILE` 형식의 대상이 아니라 문자열에 출력을 쓰고, `_swprintf_p`에서는 `count` 매개 변수가 기록할 최대 문자 수를 지정해야 한다는 점을 제외하고 `_swprintf_p` 및 `fwprintf_p`는 동일한 방식으로 동작합니다. `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 `_sprintf_p`는 종료 `NULL` 문자를 제외하고 `buffer`에 저장된 바이트 수를 반환합니다. `_swprintf_p` 에 저장 된 와이드 문자 수를 반환 `buffer`를 제외 하 고 종료 `NULL` 와이드 문자입니다. `buffer` 또는 `format`이 null 포인터이거나 형식 문자열에 잘못된 형식 지정 문자가 포함되어 있는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수가 -1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h>|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```C  
// crt_sprintf_p.c  
// This program uses _sprintf_p to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
    char     buffer[200],  
            s[] = "computer", c = 'l';  
    int      i = 35,  
            j;  
    float    fp = 1.7320534f;  
  
    // Format and print various data:   
    j  = _sprintf_p( buffer, 200,  
                     "   String:    %s\n", s );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Character: %c\n", c );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Integer:   %d\n", i );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Real:      %f\n", fp );  
  
    printf( "Output:\n%s\ncharacter count = %d\n",   
            buffer, j );  
}  
```  
  
```Output  
Output:  
   String:    computer  
   Character: l  
   Integer:   35  
   Real:      1.732053  
  
character count = 79  
```  
  
## <a name="example"></a>예  
  
```C  
// crt_swprintf_p.c  
// This is the wide character example which  
// also demonstrates _swprintf_p returning  
// error code.  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    wchar_t buffer[BUFFER_SIZE];  
    int     len;  
  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",  
                      0, L" marbles in your head.");  
    _printf_p( "Wrote %d characters\n", len );  
  
    // _swprintf_p fails because string contains WEOF (\xffff)  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",   
                      L"Hello\xffff world" );  
    _printf_p( "Wrote %d characters\n", len );  
}  
```  
  
```Output  
Wrote 24 characters  
Wrote -1 characters  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)