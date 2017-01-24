---
title: "strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbstok_l"
  - "_mbstok"
  - "wcstok"
  - "_mbstok"
  - "strtok"
  - "_wcstok_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstok"
  - "strtok"
  - "_tcstok"
  - "wcstok"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstok 함수"
  - "_mbstok_l 함수"
  - "_strtok_l 함수"
  - "_tcstok 함수"
  - "_tcstok_l 함수"
  - "_wcstok_l 함수"
  - "mbstok 함수"
  - "mbstok_l 함수"
  - "문자열[C++], 검색"
  - "strtok 함수"
  - "strtok_l 함수"
  - "tcstok 함수"
  - "tcstok_l 함수"
  - "토큰, 문자열에서 찾기"
  - "wcstok 함수"
  - "wcstok_l 함수"
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: 34
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 로캘 또는 전달된 명확한 로캘을 사용하여 문자열의 다음 토큰을 찾습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [strtok\_s, \_strtok\_s\_l, wcstok\_s, \_wcstok\_s\_l, \_mbstok\_s, \_mbstok\_s\_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  `_mbstok` 와 `_mbstok_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *strtok(  
   char *strToken,  
   const char *strDelimit   
);  
wchar_t *wcstok(  
   wchar_t *strToken,  
   const wchar_t *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `strToken`  
 토큰 또는 토큰을 포함 하는 문자열입니다.  
  
 `strDelimit`  
 구분 기호 문자 집합입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `strToken`에서 발견되는 다음 토큰에 대한 포인터를 반환합니다.  토큰이 더 이상 발견되지 않으면, `NULL` 을 반환합니다.  각 호출은 반환된 토큰 후에 발생되는 첫 번째 구분 기호 문자 `NULL` 를 대체하여 `strToken` 를 수정합니다.  
  
## 설명  
 `strtok` 함수는 `strToken`에서 다음 토큰을 찾습니다.  `strDelimit` 에서 문자 집합은 현재 호출된 `strToken` 에서 찾을 수 있는 토큰의 사용 가능한 구분 기호를 지정합니다.  `wcstok` 및 `_mbstok` 는 와이드 문자 및 `strtok`의 멀티 바이트 문자 버전입니다.  `wcstok`의 인수 및 반환 값은 와이드 문자열이며, `_mbstok`는 멀티바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
> [!IMPORTANT]
>  이러한 함수 버퍼 오버런 문제에 대한 상태로 잠재적인 위협이 발생됩니다.  버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
 첫 번째로 `strtok` 함수를 호출하면, 선행 구분 기호를 생략하고 null 문자를 사용하는 토큰을 종료하는 `strToken`에서 첫 번째 토큰에 대한 포인터를 반환합니다.  더 많은 토큰은 `strtok`에 대한 일련의 호출에 의해 `strToken` 의 나머지에서 나누어질 수 있습니다.  이 `strtok`를 호출하는 것은 각각 호출에 의해 반환된 `token` 뒤의 null 문자를 삽입하여 `strToken` 를 수정합니다,  이 `strToken`로 부터 다음 토큰에 읽혀지며, `strToken` 인수를 위한 `NULL` 값과 함께 `strtok` 을 호출합니다.  `NULL` `strToken` 인수는 수정된 `strToken` 에서 다음 토큰을 검색하는 `strtok` 을 발생시킵니다.  `strDelimit` 인수는 다음에 대한 호출에서 값을 가질 수 있기 때문에 구분 기호 집합이 달라질 수 있습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
> [!NOTE]
>  각 함수는 문자열을 토큰으로 구문 분석에 대한 정적 스레드 로컬 변수를 사용합니다.  따라서 다중 스레드에서 부작용 없이 이러한 함수를 동시에 호출할 수 있습니다.  그러나 단일 스레드 내에서, 인터리빙 호출을 이러한 함수 중 하나는 데이터 손상 및 정확하지 않은 결과가 발생할 가능성이 높습니다.  다른 문자열을 구문 분석할 때, 다음 구문 분석을 시작하기 전에 문자열 구문 분석을 완료합니다.  또한, 다른 함수가 호출 루프 내에서 이러한 함수 중 하나를 호출 할 위험에 대한 잠재적으로 인식합니다.  다른 함수 끝나면 이러한 함수 중 하나를 사용하여, 인터리브 호출 순서는 트리거 데이터 손상이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strtok`|\<string.h\>|  
|`wcstok`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strtok.c  
// compile with: /W3  
// In this program, a loop uses strtok  
// to print all the tokens (separated by commas  
// or blanks) in the string named "string".  
//  
#include <string.h>  
#include <stdio.h>  
  
char string[] = "A string\tof ,,tokens\nand some  more tokens";  
char seps[]   = " ,\t\n";  
char *token;  
  
int main( void )  
{  
   printf( "Tokens:\n" );  
  
   // Establish string and get the first token:  
   token = strtok( string, seps ); // C4996  
   // Note: strtok is deprecated; consider using strtok_s instead  
   while( token != NULL )  
   {  
      // While there are tokens in "string"  
      printf( " %s\n", token );  
  
      // Get next token:   
      token = strtok( NULL, seps ); // C4996  
   }  
}  
```  
  
  **토큰:**  
 **A**  
 **string**  
 **의**  
 **토큰**  
 **및**  
 **일부**  
 **more**  
 **토큰**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)