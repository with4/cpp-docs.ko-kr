---
title: _strdup, _wcsdup, _mbsdup | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdup
- _mbsdup
- _wcsdup
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
dev_langs: C++
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da8d1341e9ce46e2ab2040812622a78d3bd3830d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="strdup-wcsdup-mbsdup"></a>_strdup, _wcsdup, _mbsdup
문자열을 복제합니다.  
  
> [!IMPORTANT]
>  `_mbsdup`Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은                  [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `strSource`  
 Null 종료 소스 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 함수는 복사한 문자열의 저장 위치에 대한 포인터를 반환하고 저장소를 할당할 수 없는 경우에는 `NULL` 을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_strdup` 함수는 [malloc](../../c-runtime-library/reference/malloc.md)를 호출하여 `strSource` 복사본용 저장소 공간을 할당한 후 할당된 공간으로 `strSource`를 복사합니다.  
  
 `_wcsdup` 및 `_mbsdup` 는 `_strdup`의 와이드 문자 및 멀티바이트 문자 버전입니다. `_wcsdup`의 인수 및 반환 값은 와이드 문자열이며 `_mbsdup`의 인수와 반환 값은 멀티바이트 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsdup`|`_strdup`|`_mbsdup`|`_wcsdup`|  
  
 `_strdup` 는 `malloc` 를 호출하여 `strSource`복사본용 저장소 공간을 할당하기 때문에, [해제](../../c-runtime-library/reference/free.md) 루틴을 호출하는 방법으로 `_strdup`호출에서 반환되는 포인터에 대해 항상 이 메모리를 해제하는 것이 좋습니다.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC` 가 정의된 경우 메모리 할당 디버깅을 위해 `_strdup` 및 `_wcsdup` 가 `_strdup_dbg` 및 `_wcsdup_dbg` 호출에 의해 교체됩니다. 자세한 내용은 [_strdup_dbg, _wcsdup_dbg](../../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_strdup`|\<string.h>|  
|`_wcsdup`|\<string.h> 또는 \<wchar.h>|  
|`_mbsdup`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
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
Original: This is the buffer text  
Copy:     This is the buffer text  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, _mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)