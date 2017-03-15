---
title: "fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fwscanf_s"
  - "_fscanf_s_l"
  - "_fwscanf_s_l"
  - "fscanf_s"
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
  - "_fwscanf_s_l"
  - "_fscanf_s_l"
  - "fscanf_s"
  - "_ftscanf_s_l"
  - "_ftscanf_s"
  - "fwscanf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fscanf_s_l 함수"
  - "_ftscanf_s 함수"
  - "_ftscanf_s_l 함수"
  - "_fwscanf_s_l 함수"
  - "데이터[CRT], 스트림에서 읽기"
  - "서식이 지정된 데이터[C++], 스트림에서 읽기"
  - "fscanf_s 함수"
  - "fscanf_s_l 함수"
  - "ftscanf_s 함수"
  - "ftscanf_s_l 함수"
  - "fwscanf_s 함수"
  - "fwscanf_s_l 함수"
  - "스트림[C++], 서식이 지정된 데이터 읽기"
ms.assetid: b6e88194-714b-4322-be82-1cc0b343fe01
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 형식 데이터를 읽습니다.  이러한 버전의 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
## 구문  
  
```  
int fscanf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...   
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
 해당 함수는 각각 성공적으로 변환, 배정된 필드 수를 반환합니다. 이때 읽기는 되었지만 지정되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  오류가 발생하는 경우 또는 첫 번째 변환 전에 반환 값이 파일 스트림의 끝에 도달하는 경우 반환 값은 `fscanf_s` 및 `fwscanf_s`의 `EOF`가 됩니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  `stream`가 잘못된 파일 포인터가 되거나 `format`가 null 포인터가 되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명한 대로 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## 설명  
 다음 `fscanf_s` 함수는 `stream` 의 현재 위치에서 주어진 `argument` \(있을 경우\)의 지정된 위치로 데이터를 읽습니다.  목록의 각 `argument` 는 `format` 에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  `format` 은 입력 필드의 해석을 조정하고 같은 양식 컨트롤과 기능을 `scanf_s` 와 같은 `format` 인수로써 쓰입니다; `format` 에 대한 설명은 다음 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) 을 참고하십시오.  `fwscanf_s` 는 `fscanf_s` 의 와이드 문자 버전 입니다. `fwscanf_s` 는 와이드 문자 문자열입니다.  이러한 함수는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `fscanf_s`는 현재 UNICODE 스트림의 입력을 지원하지 않습니다.  
  
 보안이 강화된 함수\(`_s` 접미사 있음\)와 다른 버전 간의 주요 차이점은 보안이 강화된 함수에는 다음 변수를 인수로 즉시 전달하는 각 `c`, `C`, `s`, `S` 및 `[` 형식 필드의 문자 크기가 필요하다는 것입니다.  자세한 내용은 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) 및 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)를 참조하십시오.  
  
> [!NOTE]
>  이 크기 매개 변수는 `size_t`이 아닌 `unsigned` 형식입니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ftscanf_s`|`fscanf_s`|`fscanf_s`|`fwscanf_s`|  
|`_ftscanf_s_l`|`_fscanf_s_l`|`_fscanf_s_l`|`_fwscanf_s_l`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fscanf_s`, `_fscanf_s_l`|\<stdio.h\>|  
|`fwscanf_s`, `_fwscanf_s_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_fscanf_s.c  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   errno_t err = fopen_s( &stream, "fscanf.out", "w+" );  
   if( err )  
      printf_s( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf_s( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf_s( stream, "%s", s, _countof(s) );  
      fscanf_s( stream, "%ld", &l );  
  
      fscanf_s( stream, "%f", &fp );  
      fscanf_s( stream, "%c", &c, 1 );  
  
      // Output data read:  
      printf( "%s\n", s );  
      printf( "%ld\n", l );  
      printf( "%f\n", fp );  
      printf( "%c\n", c );  
  
      fclose( stream );  
   }  
}  
```  
  
  **문자열**  
**65000**  
**3.141590**  
**x**   
## 해당 .NET Framework 항목  
 [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx). `Parse` 메서드\(예: [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)\)도 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)