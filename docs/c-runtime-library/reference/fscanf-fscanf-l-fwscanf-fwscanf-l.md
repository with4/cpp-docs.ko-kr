---
title: "fscanf, _fscanf_l, fwscanf, _fwscanf_l | Microsoft Docs"
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
  - "fscanf"
  - "_fwscanf_l"
  - "_fscanf_l"
  - "fwscanf"
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
  - "fscanf"
  - "fwscanf"
  - "_ftscanf_l"
  - "_fwscanf_l"
  - "_ftscanf"
  - "_fscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fscanf_l 함수"
  - "_ftscanf 함수"
  - "_ftscanf_l 함수"
  - "_fwscanf_l 함수"
  - "데이터[CRT], 스트림에서 읽기"
  - "서식이 지정된 데이터[C++], 스트림에서 읽기"
  - "fscanf 함수"
  - "fscanf_l 함수"
  - "ftscanf 함수"
  - "ftscanf_l 함수"
  - "fwscanf 함수"
  - "fwscanf_l 함수"
  - "스트림[C++], 서식이 지정된 데이터 읽기"
ms.assetid: 9004e978-6c5f-4bb2-98fd-51e5948933f2
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fscanf, _fscanf_l, fwscanf, _fwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 형식 데이터를 읽습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
int fscanf(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_l(   
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
 이들 함수는 각각 성공적으로 변환, 배정된 필드 수를 반환합니다. 이때 읽기는 되었지만 지정되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  오류가 발생하는 경우 또는 첫 번째 변환 전에 반환 값이 파일 스트림의 끝에 도달하는 경우 반환 값은 `fscanf` 및 `fwscanf`의 `EOF`가 됩니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `stream` 또는 `format`이 null 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## 설명  
 다음 `fscanf` 함수는 `stream` 의 현재 위치에서 주어진 `argument` \(있을 경우\)의 지정된 위치로 데이터를 읽습니다.  목록의 각 `argument` 는 `format` 에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  `format`는 입력 필드의 해석을 컨트롤하고, `scanf`에 대한 `format` 인수와 동일한 양식과 함수를 가집니다. `format`에 대한 자세한 내용은 [scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)를 참조하십시오.  
  
 `fwscanf`는 `fscanf`의 와이드 문자 버전이며, `fwscanf`의 format 인수는 와이드 문자 문자열입니다.  이러한 함수는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `fscanf`는 현재 UNICODE 스트림의 입력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ftscanf`|`fscanf`|`fscanf`|`fwscanf`|  
|`_ftscanf_l`|`_fscanf_l`|`_fscanf_l`|`_fwscanf_l`|  
  
 자세한 내용은 [형식 사양 필드\-scanf 함수와 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)를 참조하십시오.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fscanf`, `_fscanf_l`|\<stdio.h\>|  
|`fwscanf`, `_fwscanf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fscanf.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   if( fopen_s( &stream, "fscanf.out", "w+" ) != 0 )  
      printf( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Security caution!  
      // Beware loading data from a file without confirming its size,  
      // as it may lead to a buffer overrun situation.  
  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf( stream, "%s", s );   // C4996  
      fscanf( stream, "%ld", &l ); // C4996  
  
      fscanf( stream, "%f", &fp ); // C4996  
      fscanf( stream, "%c", &c );  // C4996  
      // Note: fscanf is deprecated; consider using fscanf_s instead  
  
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
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)