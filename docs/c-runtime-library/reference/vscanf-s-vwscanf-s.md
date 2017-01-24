---
title: "vscanf_s, vwscanf_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vscanf_s"
  - "vwscanf_s"
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
  - "_vtscanf_s"
  - "vscanf_s"
  - "vwscanf_s"
dev_langs: 
  - "C++"
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vscanf_s, vwscanf_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 입력 스트림에서 형식 데이터를 읽습니다.  이러한 버전의 [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
## 구문  
  
```  
int vscanf_s(  
   const char *format,  
   va_list arglist  
);   
int vwscanf_s(  
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
 성공적으로 변환되고 할당된 필드의 수를 반환합니다. 읽기는 되지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  오류가 발생하거나 문자를 읽는 첫 번째 시도에서 파일 끝 문자나 문자열 끝 문자가 있을 경우 반환 값은 `EOF`입니다.  [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `format`이 `NULL` 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `vscanf_s` 및 `vwscanf_s`는 `EOF`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `vscanf_s` 함수는 표준 입력 스트림 `stdin`에서 데이터를 읽고 `arglist` 인수 목록에서 지정된 위치로 데이터를 씁니다.  목록의 각 인수는 `format`에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 `vwscanf_s`는 `vscanf_s`의 와이드 문자 버전이며, `vwscanf_s`의 `format` 인수는 와이드 문자 문자열입니다.  `vwscanf_s` 및 `vscanf_s`는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `vscanf_s`는 UNICODE 스트림의 입력을 지원하지 않습니다.  
  
 `vscanf` 및 `vwscanf`과 달리 `vscanf_s` 및 `vwscanf_s`에는 형식 `c`, `C`, `s`, `S`의 모든 입력 매개 변수에 지정되는 버퍼 크기 또는 `[]`에 포함된 문자열 제어 집합이 필요합니다.  문자에서 버퍼 크기는 버퍼 또는 변수에 대한 포인터 바로 다음에 추가 매개 변수로 전달됩니다.  `wchar_t` 문자열의 문자에서 버퍼 크기는 바이트 단위의 사이즈와 동일하지 않습니다.  
  
 버퍼 크기는 null 종결 문자를 포함합니다.  너비 사양 필드를 사용하여 읽은 토큰이 버퍼에 맞는지 확인할 수 있습니다.  사용된 너비 지정 필드가 없고 토큰 읽기가 버퍼 크기에 비해 너무 큰 경우 해당 버퍼에 아무것도 쓸 수 없습니다.  
  
> [!NOTE]
>  이 크기 매개 변수는 `size_t`이 아닌 `unsigned` 형식입니다.  
  
 자세한 내용은 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtscanf_s`|`vscanf_s`|`vscanf_s`|`vwscanf_s`|  
  
 자세한 내용은 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`vscanf_s`|\<stdio.h\>|  
|`wscanf_s`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_vscanf_s.c  
// compile with: /W3  
// This program uses the vscanf_s and vwscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vscanf_s(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf_s(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf_s("%d %f %c %C %s %S", &i, &fp, &c, 1,  
                           &wc, 1, s, _countof(s), ws, _countof(ws) );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf_s(L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                            &wc, 1, s, _countof(s), ws, _countof(ws) );  
    wprintf( L"The number of fields input is %d\n", result );  
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
  
```  
  
 이 프로그램에 예제의 입력이 지정될 경우 프로그램은 이 출력을 생성합니다.  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
  **필드 입력의 수는 6입니다**  
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
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md)