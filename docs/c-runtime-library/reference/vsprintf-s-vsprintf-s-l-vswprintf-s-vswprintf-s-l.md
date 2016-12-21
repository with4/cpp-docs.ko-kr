---
title: "vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l | Microsoft Docs"
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
  - "_vswprintf_s_l"
  - "vsprintf_s"
  - "vswprintf_s"
  - "_vsprintf_s_l"
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
  - "vswprintf_s"
  - "vsprintf_s"
  - "_vstprintf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vstprintf_s_l 함수"
  - "vsprintf_s_l 함수"
  - "_vstprintf_s 함수"
  - "vswprintf_s 함수"
  - "vstprintf_s 함수"
  - "vstprintf_s_l 함수"
  - "vswprintf_s_l 함수"
  - "vsprintf_s 함수"
  - "_vsprintf_s_l 함수"
  - "서식 있는 텍스트[C++]"
  - "_vswprintf_s_l 함수"
ms.assetid: 60e90518-57f0-4f1b-b732-f62a69702833
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용하여 서식이 지정된 출력을 작성합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md) 버전입니다.  
  
## 구문  
  
```  
int vsprintf_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_s_l(  
   char *buffer,  
   size_t numberOfElements,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int vswprintf_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_s_l(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int vswprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치입니다.  
  
 `numberOfElements`  
 문자에서의 `buffer` 크기 입니다.  
  
 `format`  
 형식 사양입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `vsprintf_s` 및 `vswprintf_s`는 null 종료 문자 또는 오류가 발생한 경우의 네이티브 값을 제외한 작성된 문자의 수를 반환합니다.  `buffer` 또는 `format` 는 null포인터입니다. 형식 문자열이 잘못된 형식의 문자를 포함하고 있거나 카운트가 0인 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이러한 함수의 각각은 인수 목록에 대한 포인터를 가지며, 서식을 지정하고 지정된 데이터를 `buffer` 가 가르키는 메모리에 작성합니다.  
  
 `vswprintf_s`는 `size_t` 형식의 두 번째 매개 변수인 `count`를 요구하는 `vswprintf`의 ISO C 표준을 준수합니다.  
  
 안전하지 않은 버전과 안전한 버전의 이러한 함수는 위치 매개 변수의 지원만 다릅니다.  자세한 내용은 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)을 참조하십시오.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vstprintf_s`|`vsprintf_s`|`vsprintf_s`|`vswprintf_s`|  
|`_vstprintf_s_l`|`_vsprintf_s_l`|`_vsprintf_s_l`|`_vswprintf_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`vsprintf_s`, `_vsprintf_s_l`|\<stdio.h\> 과 \<stdarg.h\>|\<varargs.h\>\*|  
|`vswprintf_s`, `_vswprintf_s_l`|\<stdio.h\> 또는 \<wchar.h\>, 및 \<stdarg.h\>|\<varargs.h\>\*|  
  
 \*는 UNIX V 호환성을 위해 필요합니다.  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_vsprintf_s.c  
// This program uses vsprintf_s to write to a buffer.  
// The size of the buffer is determined by _vscprintf.  
  
#include <stdlib.h>  
#include <stdarg.h>  
  
void test( char * format, ... )  
{  
   va_list args;  
   int len;  
   char * buffer;  
  
   va_start( args, format );  
   len = _vscprintf( format, args ) // _vscprintf doesn't count  
                               + 1; // terminating '\0'  
   buffer = malloc( len * sizeof(char) );  
   vsprintf_s( buffer, len, format, args );  
   puts( buffer );  
   free( buffer );  
}  
  
int main( void )  
{  
   test( "%d %c %d", 123, '<', 456 );  
   test( "%s", "This is a string" );  
}  
```  
  
  **123 \< 456**  
**This is a string**   
## 해당 .NET Framework 항목  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)