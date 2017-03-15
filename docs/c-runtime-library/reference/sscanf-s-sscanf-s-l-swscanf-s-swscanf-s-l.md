---
title: "sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_sscanf_s_l"
  - "sscanf_s"
  - "_swscanf_s_l"
  - "swscanf_s"
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
  - "_stscanf_s"
  - "sscanf_s"
  - "swscanf_s"
  - "_swscanf_s_l"
  - "_stscanf_s_l"
  - "_sscanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sscanf_s_l 함수"
  - "_stscanf_s 함수"
  - "_stscanf_s_l 함수"
  - "_swscanf_s_l 함수"
  - "데이터 읽기, 문자열"
  - "sscanf_s 함수"
  - "sscanf_s_l 함수"
  - "문자열[C++], 읽기"
  - "문자열[C++], 데이터 읽기"
  - "stscanf_s 함수"
  - "stscanf_s_l 함수"
  - "swscanf_s 함수"
  - "swscanf_s_l 함수"
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식이 지정 된 문자열에서 데이터를 읽습니다. 이러한 버전의 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md) 에 설명 된 대로 향상 된 보안 기능을 한 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
int sscanf_s(  
   const char *buffer,  
   const char *format [,  
   argument ] ...  
);  
int _sscanf_s_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...  
);  
int swscanf_s(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...  
);  
int _swscanf_s_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...  
);  
```  
  
#### 매개 변수  
 `buffer`  
 저장 된 데이터  
  
 `format`  
 형식 컨트롤 문자열입니다. 자세한 내용은 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)을 참조하세요.  
  
 `argument`  
 선택적 인수  
  
 `locale`  
 사용할 로캘  
  
## 반환 값  
 성공적으로 변환 되 고, 할당 되는 필드 수를 반환 하는 이러한 각 함수 반환 값에서 읽 혀 졌지만 할당 되지 않은 필드를 포함 되지 않습니다. 반환 값이 0이면 할당된 필드가 없음을 나타냅니다. 반환 값은 `EOF` 오류에 대 한 첫 번째 변환 하기 전에 문자열의 끝에 도달 하는 경우.  
  
 경우 `buffer` 또는 `format` 되는 `NULL` 에 설명 된 대로 포인터, 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용된 경우 이러한 함수가 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `sscanf_s` 함수에서 데이터를 읽는 `buffer` 각각 사용 하 여 지정 된 위치에 `argument`합니다. 형식 지정자에 해당 하는 형식이 있는 변수에 대 한 포인터를 지정 하는 형식 문자열 뒤의 인수 `format`합니다. 보안 수준 낮음 버전과 달리 `sscanf`, 버퍼 크기 매개 변수는 형식 필드 문자를 사용할 때 필요한 `c`, `C`, `s`, `S`, 묶어야 하는 컨트롤 집합을 문자열 또는 `[]`합니다. 문자에서 버퍼 크기를 필요로 하는 각 버퍼 매개 변수 바로 다음 추가 매개 변수로 제공 되어야 합니다. 예를 들어 문자열로 읽는 경우 해당 문자열에 대 한 버퍼 크기가 다음과 같이 전달 됩니다.  
  
 `wchar_t ws[10];`  
  
 `swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9`  
  
 버퍼 크기에는 종료 null이 포함되어 있습니다. 읽을 수 있는 토큰 하면 버퍼에 맞는지 확인 하는 너비 지정 필드를 사용할 수 있습니다. 너비 지정 필드가 사용되지 않으며 읽은 토큰이 너무 커서 버퍼에 맞지 않는 경우 버퍼에는 아무것도 기록되지 않습니다.  
  
 문자의 경우 다음과 같이 단일 문자를 읽을 수 있습니다.  
  
 `wchar_t wc;`  
  
 `swscanf_s(in_str, L"%c", &wc, 1);`  
  
 이 예제에서는 입력된 문자열에서 단일 문자를 읽고 및 와이드 문자 버퍼에 저장 합니다. Null로 끝나는 문자열에 대 한 여러 문자를 읽을 때 부호 없는 정수는 너비 지정 및 버퍼 크기로 사용 됩니다.  
  
 `char c[4];`  
  
 `sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 자세한 내용은 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) 및 [scanf 형식 필드 문자](../../c-runtime-library/scanf-type-field-characters.md)를 참조하세요.  
  
> [!NOTE]
>  크기 매개 변수는 `size_t`가 아니라 `unsigned` 형식입니다. 64 비트 대상을 컴파일하는 경우 정적 캐스팅을 사용 하 여 변환할 `_countof` 또는 `sizeof` 정확한 크기는 결과입니다.  
  
 `format` 인수 컨트롤 입력의 해석은 필드와 같은 형태와 기능을 `format` 에 대 한 인수는 `scanf_s` 함수입니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 `swscanf_s` 와이드 문자 버전이 `sscanf_s;` 에 대 한 인수 `swscanf_s` 는 와이드 문자 문자열입니다.`sscanf_s` 멀티 바이트 16 진수 문자를 처리 하지 않습니다.`swscanf_s` 유니코드 전자 16 진수 또는 "호환성 영역" 문자를 처리 하지 않습니다. 그렇지 않으면 `swscanf_s`과 `sscanf_s`은 동일하게 작동합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용한다는 점만 제외하고 모두 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_stscanf_s`|`sscanf_s`|`sscanf_s`|`swscanf_s`|  
|`_stscanf_s_l`|`_sscanf_s_l`|`_sscanf_s_l`|`_swscanf_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`sscanf_s`, `_sscanf_s_l`|\<stdio.h\>|  
|`swscanf_s`, `_swscanf_s_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 예제  
  
```  
// crt_sscanf_s.c  
// This program uses sscanf_s to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string plus NULL terminator  
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );  
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );  
   sscanf_s( tokenstring, "%d", &i );  
   sscanf_s( tokenstring, "%f", &fp );  
  
   // Output the data read  
   printf_s( "String    = %s\n", s );  
   printf_s( "Character = %c\n", c );  
   printf_s( "Integer:  = %d\n", i );  
   printf_s( "Real:     = %f\n", fp );  
}  
```  
  
```Output  
문자열 = 15 문자 = 1 정수: 실제 = 15: 15.000000 =  
```  
  
## 해당 .NET Framework 항목  
 참조 `Parse` 메서드를 같은 [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)합니다.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)