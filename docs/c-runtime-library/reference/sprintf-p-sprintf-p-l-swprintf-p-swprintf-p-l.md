---
title: "_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_swprintf_p"
  - "_sprintf_p_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_sprintf_p_l"
  - "_swprintf_p"
  - "sprintf_p"
  - "swprint_p_l"
  - "swprintf_p"
  - "swprintf_p_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "sprintf_p_l 함수"
  - "swprintf_p 함수"
  - "swprintf_p_l 함수"
  - "_sprintf_p 함수"
  - "_sprintf_p_l 함수"
  - "_swprintf_p 함수"
  - "sprintf_p 함수"
  - "_stprintf_p 함수"
  - "stprintf_p 함수"
  - "_swprintf_p_l 함수"
  - "stprintf_p_l 함수"
  - "서식 있는 텍스트[C++]"
  - "_stprintf_p_l 함수"
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 문자열에서 매개 변수가 사용된 순서를 지정하기 위한 기능을 사용하여 문자열로 서식이 지정된 데이터를 기록합니다.  
  
## 구문  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] …   
);  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치  
  
 `sizeOfBuffer`  
 저장할 최대 문자 수입니다.  
  
 `format`  
 형식 컨트롤 문자열  
  
 `argument`  
 선택적 인수  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 반환 값  
 기록된 문자 수이며, 오류가 발생한 경우는 \-1입니다.  
  
## 설명  
 `_sprintf_p` 함수는 일련의 문자 및 값의 서식을 지정하고 `buffer`에 저장합니다.  각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다.  형식은 일반 문자로 구성되어 있고 `printf_p` 에 대한 `format` 인수로써 동일한 형태와 함수를 가지고 있습니다.  `NULL` 문자는 기록된 마지막 문자 뒤에 추가됩니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  이 `_sprintf_p` 및 `sprintf_s` 의 다른 점은 `_sprintf_p` 가 지원 위치 매개 변수를 지원하는 것입니다. 이는 형식 문자열에서 사용되는 인수의 사용 되는 순서를 지정하는것입니다.  자세한 내용은 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)을 참조하십시오.  
  
 `_swprintf_p`는 `_sprintf_p`의 와이드 문자 버전이며, `_swprintf_p`에 대한 포인터 인수는 와이드 문자 문자열입니다.  `_swprintf_p`에서 인코딩 오류의 탐지 방식은 `_sprintf_p`와 다를 수 있습니다.  `_swprintf_p` 및 `fwprintf_p` 는 동일하게 작동하지만, `_swprintf_p` 는 `FILE` 형식의 대상 이외의 문자열에 출력을 기록하고, `_swprintf_p` 의 경우에는 `count`매개 변수로 작성할 최대 문자 수를 지정해야 합니다.  `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 `_sprintf_p` 는 `buffer` 에서 저장된 바이트들의 수를 반환하는데, 종료하는 `NULL` 문자는 제외합니다.  `_swprintf_p`는 종료 `NULL` 와이드 문자를 제외하고 `buffer`에 저장된 와이드 바이트 수를 반환합니다.  `buffer` 또는 `format` 는 null포인터입니다. 형식 문자열이 잘못된 형식의 문자를 포함하고 있을 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h\>|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
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
  
  **출력:**  
 **문자열:    computer**  
 **문자: l**  
 **정수:   35**  
 **실수:      1.732053**  
**문자 개수 \= 79**   
## 예제  
  
```  
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
  
  **24문자가 작성했습니다.**  
**\-1문자들을 작성했습니다.**   
## 해당 .NET Framework 항목  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)