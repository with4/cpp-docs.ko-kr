---
title: "fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fprintf_s_l"
  - "fwprintf_s"
  - "fprintf_s"
  - "_fwprintf_s_l"
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
  - "_ftprintf_s"
  - "fprintf_s"
  - "fwprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fprintf_s_l 함수"
  - "_ftprintf_s 함수"
  - "_ftprintf_s_l 함수"
  - "_fwprintf_s_l 함수"
  - "fprintf_s 함수"
  - "fprintf_s_l 함수"
  - "ftprintf_s 함수"
  - "ftprintf_s_l 함수"
  - "fwprintf_s 함수"
  - "fwprintf_s_l 함수"
  - "서식이 지정된 데이터를 스트림으로 인쇄"
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식이 지정된 데이터를 스트림에 출력합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) 버전입니다.  
  
## 구문  
  
```  
int fprintf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...  
);  
int _fprintf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...  
);  
int fwprintf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...  
);  
int _fwprintf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]…  
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `fprintf_s`는 쓴 바이트 수를 반환합니다.  `fwprintf_s`는 작성 된 와이드 문자의 수를 반환 합니다.  이러한 각 함수는 출력 오류가 발생했을 때 대신 음수 값을 반환합니다.  
  
## 설명  
 `fprintf_s` 는 서식을 지정하고 일련의 문자와 값을 출력`stream`*.* 에 를 출력합니다. 각 함수 `argument` \(있는 경우\) 는 `format`*.* 의 해당 형식 사양에 따라 변환되고 출력됩니다. `fprintf_s`에 대해서, `format` 인수는 `printf_s`와 동일한 구문을 사용합니다.  
  
 `fwprintf_s`는 `fprintf_s`의 와이드 문자 버전이며, `fwprintf_s`, `format`은 와이드 문자 문자열입니다.  이러한 함수는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `fprintf_s` 는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  
  
 보안이 없는 버전 같은 \([fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) 를 참조하세요\) 이러함 함수는 매개 변수의 유효성을 조사하고 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 잘못된 매개 변수 처리기를 호출합니다.`stream` 또는 `format` 가 null 포인터인 경우에도 마찬가지 입니다.  형식 문자열 자체는 또한 유효성을 검사 한다는 점에서 안전하지 않은 버전의 이러한 함수입니다.  알 수 없거나 잘못된 형식의 형식 지정자를 이러한 함수는 잘못된 매개 변수 예외를 생성합니다.  모든 종류에서, 계속해서 실행하도록 허용된 경우, 이 함수는 \-1 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ftprintf_s`|`fprintf_s`|`fprintf_s`|`fwprintf_s`|  
|`_ftprintf_s_l`|`_fprintf_s_l`|`_fprintf_s_l`|`_fwprintf_s_l`|  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fprintf_s`, `_fprintf_s_l`|\<stdio.h\>|  
|`fwprintf_s`, `_fwprintf_s_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fprintf_s.c  
// This program uses fprintf_s to format various  
// data and print it to the file named FPRINTF_S.OUT. It  
// then displays FPRINTF_S.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
  
#include <stdio.h>  
#include <process.h>  
  
FILE *stream;  
  
int main( void )  
{  
   int    i = 10;  
   double fp = 1.5;  
   char   s[] = "this is a string";  
   char   c = '\n';  
  
   fopen_s( &stream, "fprintf_s.out", "w" );  
   fprintf_s( stream, "%s%c", s, c );  
   fprintf_s( stream, "%d\n", i );  
   fprintf_s( stream, "%f\n", fp );  
   fclose( stream );  
   system( "type fprintf_s.out" );  
}  
```  
  
  **this is a string**  
**10**  
**1.500000**   
## 해당 .NET Framework 항목  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)