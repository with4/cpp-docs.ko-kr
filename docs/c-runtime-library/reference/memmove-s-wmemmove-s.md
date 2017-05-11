---
title: "memmove_s, wmemmove_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wmemmove_s
- memmove_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemmove_s
- memmove_s
dev_langs:
- C++
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ca9796f61ad5a3d65d0f421c27133cc2b458f588
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="memmoves-wmemmoves"></a>memmove_s, wmemmove_s
한 버퍼를 다른 버퍼로 이동합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      errno_t memmove_s(  
   void *dest,  
   size_t numberOfElements,  
   const void *src,  
   size_t count  
);  
errno_t wmemmove_s(  
   wchar_t *dest,  
   size_t numberOfElements,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dest`  
 대상 개체입니다.  
  
 `numberOfElements`  
 대상 버퍼의 크기입니다.  
  
 `src`  
 소스 개체입니다.  
  
 `count`  
 복사할 바이트(`memmove_s`) 또는 문자 (`wmemmove_s`) 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`dest`|`numberOfElements`|`src`|반환 값|`dest`의 내용|  
|------------|------------------------|-----------|------------------|------------------------|  
|`NULL`|any|모두|`EINVAL`|수정 안 됨|  
|any|모두|`NULL`|`EINVAL`|수정 안 됨|  
|any|< `count`|모두|`ERANGE`|수정 안 됨|  
  
## <a name="remarks"></a>설명  
 복사본 `count` 바이트의 문자를 `src` 를 `dest`합니다. 소스 영역과 대상의 일부 영역이 겹치는 경우 `memmove_s`는 겹치는 영역에서 원래 소스 바이트가 덮어쓰기 전에 복사되도록 합니다.  
  
 `dest` 또는 `src`가 null 포인터이거나 대상 문자열이 너무 작은 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우, 이러한 함수는 `EINVAL`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`memmove_s`|\<string.h>|  
|`wmemmove_s`|\<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_memmove_s.c  
//  
// The program demonstrates the   
// memmove_s function which works as expected  
// for moving overlapping regions.  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   char str[] = "0123456789";  
  
   printf("Before: %s\n", str);  
  
   // Move six bytes from the start of the string  
   // to a new position shifted by one byte. To protect against  
   // buffer overrun, the secure version of memmove requires the  
   // the length of the destination string to be specified.   
  
   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);   
  
   printf_s(" After: %s\n", str);  
}  
```  
  
## <a name="output"></a>출력  
  
```  
Before: 0123456789  
 After: 0012345789  
```  
  
## <a name="see-also"></a>참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)
