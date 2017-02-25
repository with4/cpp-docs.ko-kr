---
title: "scanf, _scanf_l, wscanf, _wscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wscanf_l"
  - "scanf"
  - "_scanf_l"
  - "wscanf"
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
  - "_tscanf"
  - "_scanf_l"
  - "wscanf"
  - "_wscanf_l"
  - "scanf"
  - "_tscanf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_scanf_l 함수"
  - "_tscanf 함수"
  - "_tscanf_l 함수"
  - "_wscanf_l 함수"
  - "데이터[C++], 입력 스트림에서 읽기"
  - "서식이 지정된 데이터[C++], 입력 스트림에서"
  - "데이터 읽기[C++], 입력 스트림에서"
  - "scanf 함수"
  - "scanf_l 함수"
  - "tscanf 함수"
  - "tscanf_l 함수"
  - "wscanf 함수"
  - "wscanf_l 함수"
ms.assetid: 73eac607-117f-4be4-9ff0-4afd9cf3c848
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# scanf, _scanf_l, wscanf, _wscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 입력 스트림에서 형식 데이터를 읽습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)을 참조하십시오.  
  
## 구문  
  
```  
int scanf(  
   const char *format [,  
   argument]...   
);  
int _scanf_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### 매개 변수  
 `format`  
 형식 컨트롤 문자열.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공적으로 변환되고 할당된 필드의 수를 반환합니다. 읽기는 되지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `format`이 `NULL` 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `scanf` 함수는 표준 입력 스트림 `stdin`에서 데이터를 읽고 `argument` 에서 주어진 위치에 데이터를 씁니다.  목록의 각 `argument` 는 `format` 에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `scanf`를 사용하여 문자열을 읽을 경우 `%s` 서식의 너비\(예: `"%s"` 대신 `"%32s"` \)를 항상 지정해야 합니다. 그렇지 않으면 서식이 적절하지 않게 지정된 입력으로 쉽게 버퍼 오버런이 발생할 수 있습니다.  또는, 다음을 사용 하십시오 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) 또는 [fgets](../../c-runtime-library/reference/fgets-fgetws.md).  
  
 `wscanf`는 `scanf`의 와이드 문자 버전이며, `wscanf`의 `format` 인수는 와이드 문자 문자열입니다.  `wscanf` 및 `scanf`는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `scanf`는 현재 UNICODE 스트림의 입력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tscanf`|`scanf`|`scanf`|`wscanf`|  
|`_tscanf_l`|`_scanf_l`|`_scanf_l`|`_wscanf_l`|  
  
 자세한 내용은 [형식 사양 필드\-scanf 함수와 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`scanf`, `_scanf_l`|\<stdio.h\>|  
|`wscanf`, `_wscanf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_scanf.c  
// compile with: /W3  
 /* This program uses the scanf and wscanf functions  
  * to read formatted input.  
  */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int   i, result;  
   float fp;  
   char  c, s[81];  
   wchar_t wc, ws[81];  
   result = scanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws ); // C4996  
   // Note: scanf and wscanf are deprecated; consider using scanf_s and wscanf_s  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
   result = wscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws ); // C4996  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
```  
  
  **`71 98.6 h z 바이트 문자 36 92.3 y n 와이드 문자`필드 입력 횟수는 6입니다.**  
**콘텐츠: 71 98.599998 h z 바이트 문자**  
**필드 입력의 수는 6입니다**  
**콘텐츠: 36 92.300003 y n 와이드 문자**   
## 해당 .NET Framework 항목  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   `Parse` 메서드\(예: [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)\)도 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)