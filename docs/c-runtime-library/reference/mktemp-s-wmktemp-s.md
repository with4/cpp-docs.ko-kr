---
title: "_mktemp_s, _wmktemp_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mktemp_s"
  - "_wmktemp_s"
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
  - "wmktemp_s"
  - "mktemp_s"
  - "_mktemp_s"
  - "_wmktemp_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktemp_s 함수"
  - "_tmktemp_s 함수"
  - "_wmktemp_s 함수"
  - "파일[C++], 임시"
  - "mktemp_s 함수"
  - "임시 파일[C++]"
  - "tmktemp_s 함수"
  - "wmktemp_s 함수"
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _mktemp_s, _wmktemp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고유한 파일 이름을 생성합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [\_mktemp, \_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 `template`  
 파일 이름 패턴입니다.  
  
 `sizeInChars`  
 `_mktemp_s`에서 싱글 바이트 문자의 크기는 널 종결자를 포함한 `_wmktemp_s`에서 와이드 문자입니다.  
  
## 반환 값  
 이러한 함수들은 모두 성공시 0을 반환하고, 실패시 오류 코드를 반환합니다.  
  
### 오류 조건  
  
|`template`|`sizeInChars`|**반환 값**|**템플릿에 새 값**|  
|----------------|-------------------|--------------|------------------|  
|`NULL`|any|`EINVAL`|`NULL`|  
|잘못된 형식입니다. \(올바른 형식에 대한 `Remarks`란을 참조하세요\)|any|`EINVAL`|빈 문자열|  
|any|\<\= X들의 수|`EINVAL`|빈 문자열|  
  
 위의 오류 조건이 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `errno`는 `EINVAL` 로 설정되고 함수는 `EINVAL`을 반환합니다.  
  
## 설명  
 `_mktemp_s`함수는 `template`인수를 수정하여 고유한 파일 이름을 생성합니다. 따라서 호출 이후 `template`포인터는 새 파일 이름을 포함하는 문자열을 가리킵니다.  `_mktemp_s` 은 최근에 사용한 멀티 바이트 코드 페이지에 따라서 멀티 바이트 문자 시퀀스를 인식하는 멀티 바이트 문자 문자열 인수를 자동적으로 적절하게 처리합니다.  `_wmktemp_s`는 `_mktemp_s`의 와이드 문자 버전이며, `_wmktemp_s`에 대한 인수는 와이드 문자 문자열입니다.  `_wmktemp_s` 및 `_mktemp_s`은 `_wmktemp_s`가 멀티 바이트 문자의 문자열을 처리하지 않는 것을 제외하고 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 `template`인수는 `baseXXXXXX`의 형식을 가집니다. `base`은 공급된 새 파일 이름의 일부이며, 각 X는 `_mktemp_s`에 의해 제공된 문자의 자리 표시자입니다.  각 자리 표시자 문자는 `template` 에서 반드시 대문자 X 여야 합니다.  `_mktemp_s`는 `base`를 보존하고 첫번째 뒤따르는 X를 알파벳 문자로 대체합니다.  `_mktemp_s`는 다음의 뒤따르는 X들을 다섯 자리 값으로 바꿉니다. 이 값은 호출 프로세스나 다중 스레드 프로그램에서 호출 스레드를 식별하는 고유 번호입니다.  
  
 `_mktemp_s`에 대한 성공적인 각 호출은 `template`을 수정합니다.  같은 `template` 인수를 사용하는 같은 프로세스 또는 같은 스레드로부터 각 후속 호출에서 `_mktemp_s` 는 이전 호출에서 `_mktemp_s` 의해 반환되는 이름과 매치 하는 파일이름에 대한 검사를 시행합니다.  지정 된 이름에 대한 파일이 없는 경우 `_mktemp_s` 는 해당 이름을 반환 합니다.  이전에 반환 된 모든 이름에 대한 파일이 있는 경우 `_mktemp_s` 는 이전에 반환된 이름을 사용할 수 있는 대\/소문자 문자를 'a'부터 'z'에서는 알파벳 문자를 대체 하여 새 이름을 만듭니다.  예를 들어, `base`인 경우는 다음과 같습니다.  
  
```  
fn  
```  
  
 그리고 `_mktemp_s`에 의해 제공된 다섯 자리 값은 12345 이며, 첫 번째 반환 된 이름은 다음과 같습니다.  
  
```  
fna12345  
```  
  
 이 이름이 FNA12345 파일을 만드는데 사용되고 파일이 여전히 존재한다면, 같은 `template`의 `base`를 가진 같은 프로세스 또는 스레드의 호출에 의해 반환되는 다음 이름은 다음과 같습니다.  
  
```  
fnb12345  
```  
  
 FNA12345이 존재하지 않는 경우, 그 다음에 반환되는 이름은 다시 다음과 같습니다.  
  
```  
fna12345  
```  
  
 `_mktemp_s`는 주어진 베이스와 템플릿 값의 모든 조합으로 최대 26개의 고유한 파일 이름을 만들 수 있습니다.  따라서 FNZ12345는 이 예제에 사용된 `base` 및 `template` 값을 만들 수 있는 마지막 고유한 파일이름 `_mktemp_s`입니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mktemp_s`|\<io.h\>|  
|`_wmktemp_s`|\<io.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## 샘플 출력  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
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
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)