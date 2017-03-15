---
title: "sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_swprintf_s_l"
  - "_sprintf_s_l"
  - "swprintf_s"
  - "sprintf_s"
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
  - "swprintf_s"
  - "sprintf_s"
  - "stdio/sprintf_s"
  - "stdio/swprintf_s"
  - "stdio/_sprintf_s_l"
  - "stdio/_swprintf_s_l"
  - "_sprintf_s_l"
  - "_swprintf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stprintf_s 함수"
  - "stprintf_s_l 함수"
  - "swprintf_s_l 함수"
  - "sprintf_s 함수"
  - "swprintf_s 함수"
  - "_swprintf_s_l 함수"
  - "sprintf_s_l 함수"
  - "_stprintf_s_l 함수"
  - "_stprintf_s 함수"
  - "_sprintf_s_l 함수"
  - "서식 있는 텍스트[C++]"
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에 서식이 지정된 데이터를 씁니다.[CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) 버전입니다.  
  
## 구문  
  
```  
int sprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   ...   
);  
int _sprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale,  
   ...   
);  
int swprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   ...  
);  
int _swprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale,  
   ...  
);  
template <size_t size>  
int sprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   ...   
); // C++ only  
template <size_t size>  
int swprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   ...  
); // C++ only  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치  
  
 `sizeOfBuffer`  
 저장할 최대 문자 수입니다.  
  
 `format`  
 형식 컨트롤 문자열  
  
 `...`  
 서식을 지정할 선택적 인수  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.  
  
## 반환 값  
 기록된 문자 수이며, 오류가 발생한 경우는 \-1입니다.`buffer` 또는 `format`이 null 포인터이면 `sprintf_s` 및 `swprintf_s`는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 `sprintf_s`는 종료 null 문자를 제외하고 `buffer`에 저장된 바이트 수를 반환합니다.`swprintf_s`는 종료 null 와이드 문자를 제외하고 `buffer`에 저장된 와이드 문자 수를 반환합니다.  
  
## 설명  
 `sprintf_s` 함수는 일련의 문자 및 값의 서식을 지정하고 `buffer`에 저장합니다. 각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다. 형식은 일반 문자로 구성되어 있으며, [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 위한 `format` 인수와 동일한 형태와 기능을 가지고 있습니다. 기록된 마지막 문자 뒤에 null 문자가 추가됩니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 `sprintf_s`와 `sprintf`의 주요 차이점은 `sprintf_s`는 유효한 서식 문자에 대한 서식 문자열을 검사하고, `sprintf`는 서식 문자열 또는 버퍼가 `NULL` 포인터인지 여부만 검사한다는 점입니다. 검사에 실패할 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 `sprintf_s`와 `sprintf`의 다른 주요 차이점은 `sprintf_s`는 출력 버퍼의 크기\(문자 수\)를 지정하는 길이 매개 변수를 사용한다는 점입니다. 종료 null을 포함하여 서식 있는 텍스트에 대해 버퍼가 너무 작은 경우 `buffer``[0]`에 null 문자를 배치하여 버퍼를 빈 문자열로 설정하면 잘못된 매개 변수 처리기가 호출됩니다.`_snprintf`와 달리 `sprintf_s`는 버퍼 크기가 0이 아닌 한 버퍼를 null로 종료합니다.  
  
 `swprintf_s`는 `sprintf_s`의 와이드 문자 버전이며, `swprintf_s`에 대한 포인터 인수는 와이드 문자 문자열입니다.`swprintf_s`에서 인코딩 오류의 탐지 방식은 `sprintf_s`와 다를 수 있습니다.`_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있어 크기 인수를 지정할 필요가 없으며, 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 버퍼가 지나치게 작은 경우에 대한 추가 제어 기능을 제공하는 `sprintf_s` 버전입니다. 자세한 내용은 [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_stprintf_s`|`sprintf_s`|`sprintf_s`|`swprintf_s`|  
|`_stprintf_s_l`|`_sprintf_s_l`|`_sprintf_s_l`|`_swprintf_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`sprintf_s`, `_sprintf_s_l`|C: \<stdio.h\><br /><br /> C\+\+: \<cstdio\> 또는 \<stdio.h\>|  
|`swprintf_s`, `_swprintf_s_l`|C: \<stdio.h\> 또는 \<wchar.h\><br /><br /> C\+\+: \<cstdio\>, \<cwchar\>, \<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_sprintf_s.c  
// This program uses sprintf_s to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );  
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );  
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );  
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );  
  
   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
```Output  
Output: String:    computer Character: l Integer:   35 Real:      1.732053 character count = 79  
```  
  
## 예제  
  
```  
// crt_swprintf_s.c  
// wide character example  
// also demonstrates swprintf_s returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf_s fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
```Output  
wrote 11 characters wrote -1 characters  
```  
  
## 해당 .NET Framework 항목  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)