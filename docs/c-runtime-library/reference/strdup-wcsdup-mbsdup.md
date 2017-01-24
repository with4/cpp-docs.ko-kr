---
title: "_strdup, _wcsdup, _mbsdup | Microsoft Docs"
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
  - "_strdup"
  - "_mbsdup"
  - "_wcsdup"
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
  - "_tcsdup"
  - "mbsdup"
  - "_mbsdup"
  - "_strdup"
  - "_ftcsdup"
  - "_wcsdup"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcsdup 함수"
  - "ftcsdup 함수"
  - "_ftcsdup 함수"
  - "mbsdup 함수"
  - "strdup 함수"
  - "_strdup 함수"
  - "_wcsdup 함수"
  - "문자열 복사"
  - "문자열 중복"
  - "복사 하는 문자열 [c + +]"
  - "_mbsdup 함수"
  - "복제 하는 문자열 [c + +]"
  - "tcsdup 함수"
  - "_tcsdup 함수"
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdup, _wcsdup, _mbsdup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 복제합니다.  
  
> [!IMPORTANT]
>  `_mbsdup`는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## 구문  
  
```  
char *_strdup(  
   const char *strSource   
);  
wchar_t *_wcsdup(  
   const wchar_t *strSource   
);  
unsigned char *_mbsdup(  
   const unsigned char *strSource   
);  
```  
  
#### 매개 변수  
 `strSource`  
 Null 종료 소스 문자열입니다.  
  
## 반환 값  
 이러한 각 함수는 복사한 문자열의 저장 위치에 대한 포인터를 반환하고 저장소를 할당할 수 없는 경우에는 `NULL`을 반환합니다.  
  
## 설명  
 `_strdup` 함수는 [malloc](../../c-runtime-library/reference/malloc.md)를 호출하여 `strSource` 복사본용 저장소 공간을 할당한 후 할당된 공간으로 `strSource`를 복사합니다.  
  
 `_wcsdup` 및 `_mbsdup`는 `_strdup`의 와이드 문자 및 멀티바이트 문자 버전입니다.`_wcsdup`의 인수 및 반환 값은 와이드 문자열이며 `_mbsdup`의 인수와 반환 값은 멀티바이트 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 `_strdup`는 `malloc`를 호출하여 `strSource` 복사본용 저장소 공간을 할당하기 때문에, [해제](../../c-runtime-library/reference/free.md) 루틴을 호출하는 방법으로 `_strdup` 호출에서 반환되는 포인터에 대해 항상 이 메모리를 해제하는 것이 좋습니다.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC`가 정의된 경우 메모리 할당 디버깅을 위해 `_strdup` 및 `_wcsdup`가 `_strdup_dbg` 및 `_wcsdup_dbg` 호출에 의해 교체됩니다. 자세한 내용은 [\_strdup\_dbg, \_wcsdup\_dbg](../../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strdup`|\<string.h\>|  
|`_wcsdup`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsdup`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_strdup.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is the buffer text";  
   char *newstring;  
   printf( "Original: %s\n", buffer );  
   newstring = _strdup( buffer );  
   printf( "Copy:     %s\n", newstring );  
   free( newstring );  
}  
```  
  
```Output  
Original: This is the buffer text Copy:     This is the buffer text  
```  
  
## 해당 .NET Framework 항목  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)