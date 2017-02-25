---
title: "scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wscanf_s"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_scanf_s_l"
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
  - "wscanf_s"
  - "_tscanf_s_l"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_tscanf_s"
  - "_scanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 [c + +] 입력 스트림에서 읽기"
  - "버퍼[C++], 버퍼 오버런"
  - "_scanf_s_l 함수"
  - "_wscanf_s_l 함수"
  - "tscanf_s_l 함수"
  - "tscanf_s 함수"
  - "scanf_s 함수"
  - "입력 스트림에서 읽기 데이터 [c + +]"
  - "wscanf_s 함수"
  - "_tscanf_s_l 함수"
  - "_tscanf_s 함수"
  - "scanf_s_l 함수"
  - "입력 스트림에서 형식이 지정 된 데이터 [c + +]"
  - "wscanf_s_l 함수"
  - "버퍼[C++], 오버런 방지"
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 입력 스트림에서 형식이 지정된 데이터를 읽습니다. 이러한 버전의 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 에 설명 된 대로 향상 된 보안 기능을 한 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### 매개 변수  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공적으로 변환되고 할당된 필드 수를 반환합니다. 이때 읽혀졌지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다. 반환 값이 0이면 할당된 필드가 없음을 나타냅니다. 오류가 발생했거나 문자를 읽는 첫 번째 시도에서 파일 끝 문자 또는 문자열 끝 문자가 발생한 경우 반환 값은 `EOF`입니다. 경우 `format` 는 `NULL` 에 설명 된 대로 포인터, 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용한 경우 `scanf_s` 및 `wscanf_s`은 `EOF`를 반환하며 `errno`는 `EINVAL`로 설정됩니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `scanf_s` 함수는 표준 입력 스트림 `stdin`에서 데이터를 읽고 `argument`에서 지정된 위치에 해당 데이터를 씁니다. 각 `argument`는 `format`의 형식 지정자에 해당되는 형식의 변수에 대한 포인터여야 합니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 `wscanf_s`은 `scanf_s`의 와이드 문자 버전이며, `format`에 대한 `wscanf_s` 인수는 와이드 문자열입니다. 스트림이 ANSI 모드에서 열리는 경우 `wscanf_s` 및 `scanf_s`가 동일하게 작동합니다.`scanf_s`는 현재 UNICODE 스트림에서의 입력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용한다는 점만 제외하고 모두 동일합니다.  
  
 `scanf` 및 `wscanf`와 달리 `scanf_s` 및 `wscanf_s`는 `c`, `C`, `s`, `S` 형식의 모든 입력 매개변수 또는 `[]`로 둘러싸인 문자열 컨트롤 집합에 대해 버퍼 크기를 지정해야 합니다. 버퍼 크기는 버퍼 또는 변수에 대한 포인터 뒤에 바로 추가 매개 변수로 전달됩니다. 예를 들어 문자열을 읽고 있는 경우 해당 문자열에 대한 버퍼 크기가 다음과 같이 전달됩니다.  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 버퍼 크기에는 종료 null이 포함되어 있습니다. 너비 지정 필드를 사용하면 읽은 토큰이 버퍼에 맞는지 확인할 수 있습니다. 너비 지정 필드가 사용되지 않으며 읽은 토큰이 너무 커서 버퍼에 맞지 않는 경우 버퍼에는 아무것도 기록되지 않습니다.  
  
> [!NOTE]
>  크기 매개 변수는 `size_t`가 아니라 `unsigned` 형식입니다. 정적 캐스트를 사용 하 여 변환 하는 `size_t` 값을 `unsigned` 64 비트에 대 한 모든 빌드 구성 합니다.  
  
 다음 예제에서는 버퍼 크기 매개 변수가 바이트가 아닌 문자의 최대 수를 설명한다는 사실을 보여 줍니다.`wscanf_s`에 대한 호출에서 버퍼 형식에 의해 지정되는 문자 너비는 형식 지정자에 의해 지정되는 문자 너비와 일치하지 않습니다.  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 `S` 형식 지정자는 함수에서 지원하는 기본 너비 "반대"인 문자 너비의 사용을 나타냅니다. 문자 너비는 싱글바이트이지만 함수는 더블바이트 문자를 지원합니다. 이 예제에서는 문자열에서 최대 9자의 싱글바이트 와이드 문자를 읽고 해당 문자를 더블바이트 와이드 문자 버퍼에 넣습니다. 문자는 싱글바이트 값으로 처리됩니다. 처음 두 문자는 `ws[0]`에 저장되고, 두 번째 두 문자는 `ws[1]`에 저장되는 방식입니다.  
  
 문자의 경우 다음과 같이 단일 문자를 읽을 수 있습니다.  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 null로 끝나는 문자열이 아닌 문자열에 대한 여러 문자를 읽을 때 정수는 너비 지정 및 버퍼 크기로 사용됩니다.  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 자세한 내용은 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 자세한 내용은 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h\>|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다. 콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 예제  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 이 프로그램을 실행하면 이 입력이 제공될 때 다음 출력이 생성됩니다.  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
이 필드 입력의 숫자는 내용이 6: 71 98.599998 h z 바이트 문자 입력 필드 수는 6 내용이: 36 92.300003 y n 와이드 문자  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   참고 항목 `Parse` 메서드를 같은 [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)합니다.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)