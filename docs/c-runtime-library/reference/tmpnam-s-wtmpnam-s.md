---
title: "tmpnam_s, _wtmpnam_s | Microsoft Docs"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
  - "L_tmpnam_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wtmpnam_s 함수"
  - "파일 이름[C++], 임시 파일 만들기"
  - "파일 이름[C++], 임시"
  - "L_tmpnam_s 상수"
  - "임시 파일, 만들기"
  - "tmpnam_s 함수"
  - "wtmpnam_s 함수"
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpnam_s, _wtmpnam_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

임시 파일을 생성하기 위해 이름을 사용할 수 있습니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 보안 향상 기능이 포함된 [tmpnam and \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) 버전입니다.  
  
## 구문  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `str`  
 생성된 이름을 보유 하는 포인터입니다.  
  
 \[in\] `sizeInChars`  
 버퍼의 크기\(문자\) 입니다.  
  
## 반환 값  
 이러한 함수는 성공시 0 을, 실패시 오류 번호를 반환 합니다.  
  
### 오류 조건  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**반환 값**|`str`의 **내용**입니다.|  
|`NULL`|any|`EINVAL`|수정 안 됨|  
|`NULL` 값이 아님\(유효한 메모리를 가리킴\)|너무 짧음|`ERANGE`|수정 안 됨|  
  
 `str`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 이러한 함수의 각각은 현재 존재하지 않는 파일의 이름을 반환합니다.  `tmpnam_s` 현재 작업 디렉터리에서의 고유 이름을 반환합니다.  파일 이름이 \\fname21와 같이 백슬래시와 경로 정보가 없이 미리 추가되면 이것은 이름이 현재 작업 디렉토리에 대해 유효함을 나타냅니다.  
  
 `tmpnam_s` 에 대해, 생성된 파일이름을 `str` 에 저장할 수 있습니다.  `tmpnam_s` 에 의해 반환 되는 문자열의 최대 길이는 STDIO.H 에 정의된 대로 `L_tmpnam_s` 입니다.  `str` 가 `NULL` 인 경우, `tmpnam_s` 는 내부 정적 버퍼에 결과를 유지합니다.  따라서 이후의 모든 호출은 값을 파괴 됩니다.  `tmpnam_s` 가 생성한 이름은 `tmpnam_s` 에 대한 첫 번째 호출 후 생성된 프로그램 파일 이름과 기본 32에 있는 일련 번호의 파일 확장자로 구성됩니다. \(.1\-.vvvvvu, when `TMP_MAX_S` in STDIO.H is INT\_MAX\)  
  
 `tmpnam_s` 는 자동적으로 멀티 바이트 문자 문자열 인수를 운영 체제에서 얻어지는 OEM 코드 페이지에 따라 멀티 바이트 문자 문자열 시퀀스를 알아보며 적절하게 처리합니다.  `_wtmpnam_s` 는 `tmpnam_s` 의 와이드 문자 버전입니다. `_wtmpnam_s` 인수와 반환 값은 와이드 문자 문자열입니다.  `_wtmpnam_s` 와 `tmpnam_s` 은 `_wtmpnam_s` 가 멀티 바이트 문자의 문자열을 처리하지 않는 것을 제외하고 동일하게 작동합니다.  
  
 C\+\+에서는 이러한 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요를 없앱니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`tmpnam_s`|\<stdio.h\>|  
|`_wtmpnam_s`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)