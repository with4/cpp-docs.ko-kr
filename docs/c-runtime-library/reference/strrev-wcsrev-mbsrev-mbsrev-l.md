---
title: "_strrev, _wcsrev, _mbsrev, _mbsrev_l | Microsoft Docs"
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
  - "_wcsrev"
  - "_mbsrev"
  - "_strrev"
  - "_mbsrev_l"
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
  - "_strrev"
  - "_ftcsrev"
  - "_tcsrev"
  - "mbsrev"
  - "mbsrev_l"
  - "_wcsrev_fstrrev"
  - "_mbsrev"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsrev 함수"
  - "_mbsrev 함수"
  - "_mbsrev_l 함수"
  - "_strrev 함수"
  - "_tcsrev 함수"
  - "_wcsrev 함수"
  - "문자[C++], 순서 반전"
  - "문자[C++], 전환"
  - "ftcsrev 함수"
  - "mbsrev 함수"
  - "mbsrev_l 함수"
  - "문자열의 문자 역순으로"
  - "문자열[C++], 역순"
  - "strrev 함수"
  - "tcsrev 함수"
  - "wcsrev 함수"
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strrev, _wcsrev, _mbsrev, _mbsrev_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열의 문자를 반전시킵니다.  
  
> [!IMPORTANT]
>  `_mbsrev` 와 `_mbsrev_l` 는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_strrev(  
   char *str   
);  
wchar_t *_wcsrev(  
   wchar_t *str   
);  
unsigned char *_mbsrev(  
   unsigned char *str   
);  
unsigned char *_mbsrev_l(  
   unsigned char *str,  
   _locale_t locale   
);  
```  
  
#### 매개 변수  
 `str`  
 반전할 Null 종료 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 변경된 문자열에 대한 포인터를 반환합니다.  반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.  
  
## 설명  
 `_strrev`  함수는   `string` 의 문자 순서를 반대로 바꿉니다.   종료 null 문자는 위치에 남아 있습니다.  `_wcsrev` 및 `_mbsrev` 는 와이드 문자 및 `_strrev`의 멀티 바이트 문자 버전입니다.  `_wcsrev`의 인수 및 반환 값은 와이드 문자열이며, `_mbsrev`는 멀티바이트 문자열입니다.   `_mbsrev` 에 대하여,  `string` 의 멀티 바이트 각 문자의 바이트 순서는 변경되지 않습니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 `_mbsrev` 매개 변수의 유효성을 검사합니다.  이 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `string1` 또는 `string2` 어느 쪽이 null 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `_mbsrev` 는 `NULL` 을 반환하고, `errno` 에 `EINVAL`를 설정합니다.  `_strrev` 와 `_wcsrev` 는 매개 변수를 확인 하지 않습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 버전이 현재 로캘을 사용하거나 `_l` 접미사가 있는 버전이 전달된 로캘 매개 변수 대신일 경우를 제외하고는 해당 함수의 버전과 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다.  버퍼 오버런은 불필요한 권한 상승을 발생시킬 수 있으므로 시스템 공격에 사용될 수 있습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsrev`|`_strrev`|`_mbsrev`|`_wcsrev`|  
|**해당 없음**|**해당 없음**|`_mbsrev_l`|**해당 없음**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strrev`|\<string.h\>|  
|`_wcsrev`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsrev`, `_mbsrev_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strrev.c  
// This program checks a string to see  
// whether it is a palindrome: that is, whether  
// it reads the same forward and backward.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* string = "Able was I ere I saw Elba";  
   int result;  
  
   // Reverse string and compare (ignore case):  
   result = _stricmp( string, _strrev( _strdup( string ) ) );  
   if( result == 0 )  
      printf( "The string \"%s\" is a palindrome\n", string );  
   else  
      printf( "The string \"%s\" is not a palindrome\n", string );  
}  
```  
  
  **문자열 "Able was I ere I saw Elba"은 회문입니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)