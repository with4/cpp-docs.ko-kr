---
title: "_mktemp, _wmktemp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmktemp"
  - "_mktemp"
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
  - "_tmktemp"
  - "wmktemp"
  - "tmktemp"
  - "_wmktemp"
  - "_mktemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktemp 함수"
  - "_tmktemp 함수"
  - "_wmktemp 함수"
  - "파일[C++], 임시"
  - "mktemp 함수"
  - "임시 파일[C++]"
  - "tmktemp 함수"
  - "wmktemp 함수"
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _mktemp, _wmktemp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고유한 파일 이름을 생성합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_mktemp\_s, \_wmktemp\_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md)를 참조하십시오.  
  
## 구문  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 `template`  
 파일 이름 패턴입니다.  
  
## 반환 값  
 각 함수는 수정된 템플릿에 대한 포인터를 반환합니다.  함수는 `template` 가 잘못 된 형식 또는 템플릿에서 더 이상 특정한 이름을 만들 수 없는 경우에 `NULL` 을 반환합니다.  
  
## 설명  
 `_mktemp` 함수는 `template` 인수를 수정하여 고유한 파일 이름을 생성합니다.  `_mktemp` 은 최근에 사용한 멀티 바이트 코드 페이지에 따라서 멀티 바이트 문자 시퀀스를 인식하는 멀티 바이트 문자 문자열 인수를 자동적으로 적절하게 처리합니다.  `_wmktemp` 는 `_mktemp` 의 와이드 문자 버전입니다. `_wmktemp` 인수와 반환 값은 와이드 문자 문자열입니다.  `_wmktemp` 및 `_mktemp` 은 `_wmktemp` 가 멀티 바이트 문자 문자열을 처리 하지 않는 것을 제외하고 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 `template` 인수는 `base` 가 사용자가 제공하는 파일 이름의 일부분이 있고 각 X가 `_mktemp` 에서 제공하는 문자에 대한 문자 자리 표시자인  `base`XXXXXX 형식을 가집니다.  각 자리 표시자 문자는 `template` 에서 반드시 대문자 X 여야 합니다.  `_mktemp` 는 `base` 를 보존하고 뒤에 오는 첫 번째 X 알파벳 문자로 바꿉니다.  `_mktemp` 는 X의 뒤 5 자리 숫자 값을 바꿉니다 이 값은 다중 스레드 프로그램을 호출 하는 스레드 또는 프로세스를 호출 할 때 식별 하는 고유 번호입니다.  
  
 `_mktemp` 에 대한 성공적인 각 호출은 `template` 을 수정합니다.  같은 `template` 인수를 사용하는 같은 프로세스 또는 같은 스레드로부터 각 후속 호출에서 `_mktemp` 는 이전 호출에서 `_mktemp` 의해 반환되는 이름과 매치 하는 파일이름에 대한 검사를 시행합니다.  지정 된 이름에 대한 파일이 없는 경우 `_mktemp` 는 해당 이름을 반환 합니다.  이전에 반환 된 모든 이름에 대한 파일이 있는 경우 `_mktemp` 는 이전에 반환된 이름을 사용할 수 있는 대\/소문자 문자를 'a'부터 'z'에서는 알파벳 문자를 대체 하여 새 이름을 만듭니다.  예를 들어, `base` 인 경우:  
  
```  
fn  
```  
  
 `_mktemp` 에 의해 제공된 다섯 자리 값은 12345 이며, 첫 번째 반환 된 이름은 :  
  
```  
fna12345  
```  
  
 만약 이 이름이 FNA12345 파일을 만드는데 사용되고 파일이 여전히 존재 한다면, `template` 에 대해 같은 `base` 을 사용하는 같은 프로세스 또는 스레드에서의 호출에서 반환 되는 다른 이름은:  
  
```  
fnb12345  
```  
  
 FNA12345 이 존재 하지 않는 경우, 다시 반환 된 다음 이름은 :  
  
```  
fna12345  
```  
  
 `_mktemp` 는 자료 및 서식 파일의 특정된 조합에 대해 고유한 파일 이름을 최대 16개 만들 수 있습니다.  따라서 FNZ12345 은 이 예제에서 사용 되는 `base` 및 `template` 값에 대해 생성 될 수 있는 마지막 고유 파일이름 `_mktemp` 입니다.  
  
 오류 시, `errno` 가 설정됩니다.  `template` 가 잘못된 형식을 가지는 경우 \( 예를 들어 X의 6보다 적은 수\), `errno` 가 `EINVAL` 로 설정됩니다.  모든 26개의 가능한 파일 이름이 이미 존재하기 때문에 `_mktemp` 가 고유의 이름을 생성하는데 사용할 수 없는 경우, `_mktemp` 는 템플릿을 빈 문자열로 설정하고 `EEXIST` 를 반환합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mktemp`|\<io.h\>|  
|`_wmktemp`|\<io.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
  **Fna03912는 고유 이름입니다.**  
**fnb03912는 고유 이름입니다.**  
**fnc03912는 고유 이름입니다.**  
**fnd03912는 고유 이름입니다.**  
**fne03912는 고유 이름입니다.**  
**fnf03912는 고유 이름입니다.**  
**fng03912는 고유 이름입니다.**  
**fnh03912는 고유 이름입니다.**  
**fni03912는 고유 이름입니다.**  
**fnj03912는 고유 이름입니다.**  
**fnk03912는 고유 이름입니다.**  
**fnl03912는 고유 이름입니다.**  
**fnm03912는 고유 이름입니다.**  
**fnn03912는 고유 이름입니다.**  
**fno03912는 고유 이름입니다.**  
**fnp03912는 고유 이름입니다.**  
**fnq03912는 고유 이름입니다.**  
**fnr03912는 고유 이름입니다.**  
**fns03912는 고유 이름입니다.**  
**fnt03912는 고유 이름입니다.**  
**fnu03912는 고유 이름입니다.**  
**fnv03912는 고유 이름입니다.**  
**fnw03912는 고유 이름입니다.**  
**fnx03912는 고유 이름입니다.**  
**fny03912는 고유 이름입니다.**  
**fnz03912는 고유 이름입니다.**  
**템플릿 생성시 문제**  
**고유한 파일이름 부족**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_getpid](../../c-runtime-library/reference/getpid.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)