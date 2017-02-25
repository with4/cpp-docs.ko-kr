---
title: "sscanf, _sscanf_l, swscanf, _swscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "swscanf"
  - "sscanf"
  - "_sscanf_l"
  - "_swscanf_l"
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
  - "_sscanf_l"
  - "_stscanf"
  - "swscanf"
  - "_stscanf_l"
  - "sscanf"
  - "_swscanf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sscanf_l 함수"
  - "_stscanf 함수"
  - "_stscanf_l 함수"
  - "_swscanf_l 함수"
  - "데이터 읽기, 문자열"
  - "sscanf 함수"
  - "sscanf_l 함수"
  - "문자열[C++], 읽기"
  - "문자열[C++], 데이터 읽기"
  - "stscanf 함수"
  - "stscanf_l 함수"
  - "swscanf 함수"
  - "swscanf_l 함수"
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# sscanf, _sscanf_l, swscanf, _swscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에서 형식 데이터를 읽습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
int sscanf(  
   const char *buffer,  
   const char *format [,  
   argument ] ...   
);  
int _sscanf_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...   
);  
int swscanf(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...   
);  
int _swscanf_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...   
);  
```  
  
#### 매개 변수  
 `buffer`  
 저장된 데이터  
  
 `format`  
 형식 컨트롤 문자열입니다.  자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)을 참조하십시오.  
  
 `argument`  
 선택적 인수  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이들 함수는 각각 성공적으로 변환, 배정된 필드 수를 반환합니다. 이때 읽기는 되었지만 지정되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  오류가 발생하거나 첫 번째 변환 전에 문자열의 끝에 도달할 경우 반환 값은 `EOF`입니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `buffer` 또는 `format`이 `NULL` 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `sscanf` 함수는 각 `argument`로 부터 주어진 로캘의 `buffer` 로 부터 데이터를 읽습니다.  목록의 모든 `argument` 는 `format` 에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  `format` 인수는 입력 필드의 해석을 제어하고 `scanf` 함수의 `format` 인수와 동일한 폼과 함수를 가집니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `sscanf`를 사용하여 문자열을 읽을 경우 `%s` 서식의 너비\(예: `"%s"` 대신 `"%32s"` \)를 항상 지정해야 합니다. 그렇지 않으면 서식이 적절하지 않게 지정된 입력으로 쉽게 버퍼 오버런이 발생할 수 있습니다.  
  
 `swscanf`는 `sscanf`의 와이드 문자 버전이며, `swscanf`에 대한 인수는 와이드 문자 문자열입니다.  `sscanf`는 멀티 바이트 16진수 문자를 처리하지 않습니다.  `swscanf` 는 "호환성 영역" 문자들 또는 유니코드 최대 넓이의 16진수를 처리하지 않습니다.  그렇지 않으면 `swscanf`과 `sscanf`은 동일하게 작동합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_stscanf`|`sscanf`|`sscanf`|`swscanf`|  
|`_stscanf_l`|`_sscanf_l`|`_sscanf_l`|`_swscanf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`sscanf`, `_sscanf_l`|\<stdio.h\>|  
|`swscanf`, `_swscanf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_sscanf.c  
// compile with: /W3  
// This program uses sscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string:  
   sscanf( tokenstring, "%80s", s ); // C4996  
   sscanf( tokenstring, "%c", &c );  // C4996  
   sscanf( tokenstring, "%d", &i );  // C4996  
   sscanf( tokenstring, "%f", &fp ); // C4996  
   // Note: sscanf is deprecated; consider using sscanf_s instead  
  
   // Output the data read  
   printf( "String    = %s\n", s );  
   printf( "Character = %c\n", c );  
   printf( "Integer:  = %d\n", i );  
   printf( "Real:     = %f\n", fp );  
}  
```  
  
  **문자열    \= 15**  
**문자 \= 1**  
**정수: \= 15**  
**실수:     \= 15.000000**   
## 해당 .NET Framework 항목  
 `Parse` 메서드\(예: [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)\)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)