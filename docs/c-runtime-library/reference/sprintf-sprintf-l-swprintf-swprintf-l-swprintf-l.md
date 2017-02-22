---
title: "sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__swprintf_l"
  - "sprintf"
  - "_sprintf_l"
  - "_swprintf_l"
  - "swprintf"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_stprintf_l"
  - "__swprintf_l"
  - "sprintf_l"
  - "swprintf"
  - "_sprintf_l"
  - "sprintf"
  - "_stprintf"
  - "stprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__swprintf_l 함수"
  - "_CRT_NON_CONFORMING_SWPRINTFS"
  - "_sprintf_l 함수"
  - "_stprintf 함수"
  - "_stprintf_l 함수"
  - "_swprintf_l 함수"
  - "서식 있는 텍스트[C++]"
  - "sprintf 함수"
  - "sprintf_l 함수"
  - "stprintf 함수"
  - "stprintf_l 함수"
  - "문자열[C++], 쓰기"
  - "swprintf 함수"
  - "swprintf_l 함수"
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
caps.latest.revision: 36
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 36
---
# sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에 서식이 지정된 데이터를 씁니다.  이러한 함수 중 일부의 더 안전한 버전을 사용할 수 있습니다. [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)을 참조하세요.  `swprintf` 및 `_swprintf_l`의 안전한 버전에서는 `count` 매개 변수를 사용하지 않습니다.  
  
## 구문  
  
```  
int sprintf(  
   char *buffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int swprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
int __swprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int sprintf(  
   char (&buffer)[size],  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _sprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치  
  
 `count`  
 이 함수의 유니코드 버전에 저장할 최대 문자 수입니다.  
  
 `format`  
 형식 컨트롤 문자열  
  
 `argument`  
 선택적 인수  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.  
  
## 반환 값  
 기록된 문자 수이며, 오류가 발생한 경우는 \-1입니다.  `buffer` 또는 `format`가 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우 이러한 함수가 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 `sprintf`는 종료 null 문자를 제외하고 `buffer`에 저장된 바이트 수를 반환합니다.  `swprintf`는 종료 null 와이드 문자를 제외하고 `buffer`에 저장된 와이드 문자 수를 반환합니다.  
  
## 설명  
 `sprintf` 함수는 일련의 문자 및 값의 서식을 지정하고 `buffer`에 저장합니다.  각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다.  형식은 일반 문자로 구성되어 있으며, `format`printf를 위한 [인수와 동일한 형태와 기능을 가지고 있습니다.](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 기록된 마지막 문자 뒤에 null 문자가 추가됩니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `sprintf`를 사용하는 경우 기록되는 문자 수를 제한할 방법이 없습니다. 즉, `sprintf`를 사용하는 코드에서는 버퍼 오버런이 발생하기 쉽습니다.  `buffer`에 기록되는 최대 문자 수를 지정하는 관련 함수 [\_snprintf](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)를 사용하거나, [\_scprintf](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md)를 사용하여 필요한 버퍼 크기를 결정합니다.  또한 `format`이 사용자 정의 문자열이 아닌지 확인합니다.  
  
 `swprintf`는 `sprintf`의 와이드 문자 버전이며, `swprintf`에 대한 포인터 인수는 와이드 문자 문자열입니다.  `swprintf`에서 인코딩 오류의 탐지 방식은 `sprintf`와 다를 수 있습니다.  `swprintf`는 `FILE` 형식의 대상이 아니라 문자열에 출력을 쓰고, `swprintf`에서는 `count` 매개 변수가 기록할 최대 문자 수를 지정해야 한다는 점을 제외하고 `swprintf` 및 `fwprintf`는 동일한 방식으로 동작합니다.  `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 `swprintf`는 `size_t` 형식의 두 번째 매개 변수 `count`를 요구하는 ISO C 표준을 준수합니다.  기존 비표준 동작을 강제 적용하려면 `_CRT_NON_CONFORMING_SWPRINTFS`를 정의합니다.  이후 버전에서 기존 동작이 제거될 수도 있으므로 새 준수 동작을 사용하도록 코드를 변경해야 합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_stprintf`|`sprintf`|`sprintf`|`_swprintf`|  
|`_stprintf_l`|`_sprintf_l`|`_sprintf_l`|`__swprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`sprintf`, `_sprintf_l`|\<stdio.h\>|  
|`swprintf`, `_swprintf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
```  
// crt_sprintf.c  
// compile with: /W3  
// This program uses sprintf to format various  
// data and place them in the string named buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996  
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996  
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996  
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996  
   // Note: sprintf is deprecated; consider using sprintf_s instead  
  
   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
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
// crt_swprintf.c  
// wide character example  
// also demonstrates swprintf returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
  **11자를 썼습니다.**  
**\-1자를 썼습니다.**   
## 해당 .NET Framework 항목  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)