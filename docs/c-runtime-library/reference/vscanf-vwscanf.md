---
title: "vscanf, vwscanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vscanf"
  - "vwscanf"
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
  - "vscanf"
  - "vwscanf"
  - "_vtscanf"
dev_langs: 
  - "C++"
ms.assetid: d1df595b-11bc-4682-9441-a92616301e3b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# vscanf, vwscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 입력 스트림에서 형식 데이터를 읽습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [vscanf\_s, vwscanf\_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md)을 참조하십시오.  
  
## 구문  
  
```  
int vscanf(  
   const char *format,  
   va_list arglist  
);  
int vwscanf(  
   const wchar_t *format,  
   va_list arglist  
);  
  
```  
  
#### 매개 변수  
 `format`  
 형식 컨트롤 문자열.  
  
 `arglist`  
 가변 길이 인수 목록.  
  
## 반환 값  
 성공적으로 변환되고 할당된 필드의 수를 반환합니다. 읽기는 되지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `format`이 `NULL` 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `vscanf` 함수는 표준 입력 스트림 `stdin`에서 데이터를 읽고 `arglist` 인수 목록에서 지정된 위치로 데이터를 씁니다.  목록의 각 인수는 `format`에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `vscanf`를 사용하여 문자열을 읽을 경우 `%s` 서식의 너비\(예: `"%s"` 대신 `"%32s"`\)를 항상 지정해야 합니다. 그렇지 않으면 서식이 잘못 지정된 입력으로 버퍼 오버런이 발생할 수 있습니다.  아니면 [vscanf\_s, vwscanf\_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md) 또는 [fgets](../../c-runtime-library/reference/fgets-fgetws.md)를 사용할 수 있습니다.  
  
 `vwscanf`는 `vscanf`의 와이드 문자 버전이며, `vwscanf`의 `format` 인수는 와이드 문자 문자열입니다.  `vwscanf` 및 `vscanf`는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `vscanf`는 UNICODE 스트림의 입력을 지원하지 않습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtscanf`|`vscanf`|`vscanf`|`vwscanf`|  
  
 자세한 내용은 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`vscanf`|\<stdio.h\>|  
|`vwscanf`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_vscanf.c  
// compile with: /W3  
// This program uses the vscanf and vwscanf functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vscanf(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws );  
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
 [vscanf\_s, vwscanf\_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md)