---
title: "_tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs"
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
  - "_wtempnam"
  - "_wtmpnam"
  - "tmpnam"
  - "_tempnam"
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
  - "wtempnam"
  - "_wtmpnam"
  - "wtmpnam"
  - "tmpnam"
  - "_wtempnam"
  - "_tempnam"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tempnam 함수"
  - "_ttmpnam 함수"
  - "_wtempnam 함수"
  - "_wtmpnam 함수"
  - "파일 이름[C++], 임시 파일 만들기"
  - "파일 이름[C++], 임시"
  - "tempnam 함수"
  - "임시 파일, 만들기"
  - "tmpnam 함수"
  - "ttmpnam 함수"
  - "wtempnam 함수"
  - "wtmpnam 함수"
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _tempnam, _wtempnam, tmpnam, _wtmpnam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

임시 파일을 생성하기 위해 이름을 사용할 수 있습니다.  일부 기능의 더 안전한 버전을 사용할 수 있습니다. [tmpnam\_s, \_wtmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)을 참조하십시오.  
  
## 구문  
  
```  
char *_tempnam(  
   const char *dir,  
   const char *prefix   
);  
wchar_t *_wtempnam(  
   const wchar_t *dir,  
   const wchar_t *prefix   
);  
char *tmpnam(  
   char *str   
);  
wchar_t *_wtmpnam(  
   wchar_t *str   
);  
```  
  
#### 매개 변수  
 `prefix`  
 `_tempnam` 가 반환하는 이름에 대해 미리 추가될 문자열입니다.  
  
 `dir`  
 TMP 환경 변수가 없거나 TMP가 유효한 디렉터리가 아닌경우, 경로는 파일이름에서 사용됩니다.  
  
 `str`  
 생성된 이름을 가지고 함수에 의해 반환되는 이름과 동일한 포인터입니다.  이것은 생성된 이름을 편리하게 저장합니다.  
  
## 반환 값  
 실패한 경우, 이러한 함수의 각각은 생성되거나 `NULL` 인 이름에 대한 포인터를 반환합니다.  `tmpnam` 를 사용하여 `TMP_MAX` 를\(STDIO.H 를 참조하십시오\) 더 호출하는 경우나 `_tempnam` 를 사용하는 경우 실패가 발생하고 TMP 환경 변수와 `dir` 매개 변수에서 지정하는 잘못된 디렉터리 이름이 됩니다.  
  
> [!NOTE]
>  `tmpnam` 가 포인터를 반환하고 `_wtmpnam` 는 내부 정적 버퍼를 가르킵니다.  [free](../../c-runtime-library/reference/free.md) 는 이러한 포인터의 할당을 해제하기 위해 호출할 수 없습니다.  `free` 는 `_tempnam` 및 `_wtempnam` 에 의해 할당된 포인터에대해 호출되어야 합니다.  
  
## 설명  
 이러한 함수의 각각은 현재 존재하지 않는 파일의 이름을 반환합니다.  `tmpnam` 는 현재 작업 디렉토리에서 고유 이름을 반환하고 `_tempnam` 는 현재 디렉터리외에서 고유 이름을 생성하게 합니다.  파일 이름이 \\fname21와 같이 백슬래시와 경로 정보가 없이 미리 추가되면 이것은 이름이 현재 작업 디렉토리에 대해 유효함을 나타냅니다.  
  
 `tmpnam` 에 대해, 생성된 파일이름을 `str` 에 저장할 수 있습니다.  `str` 가 `NULL` 인 경우, `tmpnam` 는 내부 정적 버퍼에 결과를 유지합니다.  따라서 이후의 모든 호출은 값을 파괴 됩니다.  `tmpnam` 가 생성한 이름은 `tmpnam` 에 대한 첫 번째 호출 후 생성된 프로그램 파일 이름과 기본 32에 있는 일련 번호의 파일 확장자로 구성됩니다. \(.1\-.vvu, when `TMP_MAX` in STDIO.H is 32,767\)  
  
 `_tempnam` 는 다음 규칙에 따라 선택한 디렉터리에 고유한 파일 이름을 생성 합니다.  
  
-   TMP 환경 변수가 정의 되고 유효한 디렉터리 이름으로 설정한 경우, 고유한 파일 이름은 TMP 디렉토리에 생성 됩니다.  
  
-   TMP 환경 변수가 정의 되지 않은 경우 또는 존재 하지 않는 디렉터리의 이름으로 설정 된 경우, `_tempnam` 는 생성될 고유이름에 대해 경로로 `dir` 매개 변수를 사용합니다.  
  
-   TMP 환경 변수가 정의 되지 않은 경우 또는 존재 하지 않는 디렉터리의 이름으로 설정 되고, `dir` 가 `NULL` 이거나 존재 하지 않는 디렉터리의 이름으로 설정한 경우, `_tempnam` 는 고유 이름을 생성 하기위해 현재 작업 디렉터리를 사용 합니다.  현재 TMP 및 `dir` 가 존재 하지 않는 디렉터리의 이름을 지정 하면 `_tempnam` 함수 호출은 실패 합니다.  
  
 `_tempnam` 가 반환하는 이름은 지정된 디렉터리에 대한 고유 파일이름을 생성하기 위해 결합하는 `prefix` 와 일련 번호의 연속이 됩니다.  `_tempnam` 는 확장명이 없는 파일 이름을 생성 합니다.  `_tempnam` 는 [malloc](../../c-runtime-library/reference/malloc.md)를 사용하여 파일 이름에 대해 공간을 할당합니다. 프로그램은 이 공간이 더 이상 필요하지 않으면 이 공간을 해제 해야 합니다.  
  
 `_tempnam` 및 `tmpnam` 는 자동적으로 멀티 바이트 문자 문자열 인수를 운영 체제에서 얻어지는 OEM 코드 페이지에 따라 멀티 바이트 문자 문자열 시퀀스를 알아보며 적절하게 처리합니다.  `_wtempnam` 는 `_tempnam` 의 와이드 문자 버전입니다. `_wtempnam` 인수와 반환 값은 와이드 문자 문자열입니다.  `_wtempnam` 와 `_tempnam` 은 `_wtempnam` 가 멀티 바이트 문자의 문자열을 처리하지 않는 것을 제외하고 동일하게 작동합니다.  `_wtmpnam` 는 `tmpnam` 의 와이드 문자 버전입니다. `_wtmpnam` 인수와 반환 값은 와이드 문자 문자열입니다.  `_wtmpnam` 와 `tmpnam` 은 `_wtmpnam` 가 멀티 바이트 문자의 문자열을 처리하지 않는 것을 제외하고 동일하게 작동합니다.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC` 가 정의된 경우, `_tempnam` 및 `_wtempnam` 는 [\_tempnam\_dbg and \_wtempnam\_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md) 에 대한 호출로 대체 됩니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_tempnam`|\<stdio.h\>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h\> 또는 \<wchar.h\>|  
|`tmpnam`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_tempnam.c  
// compile with: /W3  
// This program uses tmpnam to create a unique filename in the  
// current working directory, then uses _tempnam to create   
// a unique filename with a prefix of stq.   
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char* name1 = NULL;  
   char* name2 = NULL;  
  
   // Create a temporary filename for the current working directory:   
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996  
   // Note: tmpnam is deprecated; consider using tmpnam_s instead  
      printf( "%s is safe to use as a temporary file.\n", name1 );  
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // Create a temporary filename in temporary directory with the  
   // prefix "stq". The actual destination directory may vary  
   // depending on the state of the TMP environment variable and  
   // the global variable P_tmpdir.     
  
   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )  
      printf( "%s is safe to use as a temporary file.\n", name2 );   
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // When name2 is no longer needed :     
   if(name2)  
     free(name2);  
  
}  
```  
  
  **\\s1gk. is safe to use as a temporary file.**  
**C:\\DOCUME~1\\user\\LOCALS~1\\Temp\\2\\stq2 is safe to use as a temporary file.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)