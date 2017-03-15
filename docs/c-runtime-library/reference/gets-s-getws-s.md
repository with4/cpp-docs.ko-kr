---
title: "gets_s, _getws_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws_s"
  - "gets_s"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getws_s"
  - "gets_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getws_s 함수"
  - "버퍼 오버런"
  - "버퍼, 오버런 방지"
  - "버퍼, 버퍼 오버런"
  - "gets_s 함수"
  - "getws_s 함수"
  - "선, 가져오기"
  - "표준 입력, 읽기"
  - "스트림, 줄 가져오기"
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# gets_s, _getws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`stdin` 스트림에서 줄을 가져옵니다.  이러한 버전의 [gets, \_getws](../../c-runtime-library/gets-getws.md) 에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
## 구문  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `buffer`  
 입력 문자열에 대한 저장 위치입니다.  
  
 \[in\] `sizeInCharacters`  
 버퍼의 크기입니다.  
  
## 반환 값  
 성공하면 `buffer`를 반환합니다.   `NULL` 포인터는 오류나 파일의 끝 조건을 나타냅니다.  어떤 것이 발생했는지 확인 하려면 [ferror](../../c-runtime-library/reference/ferror.md) 또는 [feof](../../c-runtime-library/reference/feof.md) 를 사용하십시오.  
  
## 설명  
 `gets_s` 함수는 표준 입력 스트림 `stdin` 에서 읽은 줄을 `buffer` 에 저장합니다.  줄은 첫 번째 줄 바꿈 문자 \('\\n'\)까지 모든 문자로 구성 됩니다.  `gets_s` 는 줄을 반환하기 전에 줄 바꿈 문자를 Null 문자\('\\0'\) 로 대체합니다.  반면에, `fgets_s` 함수는 줄 바꿈 문자를 유지 합니다.  
  
 만약 첫번째 문자가 파일 끝 문자라면, null 문자가 `buffer` 의 시작 부분에 저장되고 `NULL` 값이 반환됩니다.  
  
 `_getws` 는 `gets_s` 의 와이드 문자 버전입니다. 해당 인수와 반환 값은 와이드 문자 문자열입니다.  
  
 `buffer` 가 `NULL` 이거나 `sizeInCharacters` 가 0 또는 0보다 작은경우나 버퍼가 너무 작아서 입력 줄과 null 종결자를 포함하지 못하는 경우, 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 잘못된 매개 변수 핸들러를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `NULL` 를 반환하고 errno를 `ERANGE` 로 설정합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`gets_s`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
  **`Hello there!`The line entered was: Hello there\!**   
## 해당 .NET Framework 항목  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)