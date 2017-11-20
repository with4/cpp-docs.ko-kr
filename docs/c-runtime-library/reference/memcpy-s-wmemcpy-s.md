---
title: "memcpy_s, wmemcpy_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy_s
- wmemcpy_s
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
- wmemcpy_s
- memcpy_s
dev_langs: C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac0b4cd7783cd41d480777fe8116a0facea58a28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s
버퍼 간에 바이트를 복사합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dest`  
 새 버퍼입니다.  
  
 `destSize`  
 대상 버퍼의 크기로, memcpy_s의 경우 바이트 단위이고 wmemcpy_s의 경우 와이드 문자(wchar_t) 단위입니다.  
  
 `src`  
 복사할 버퍼입니다.  
  
 `count`  
 복사할 문자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`dest`|`destSize`|`src`|`count`|반환 값|`dest`의 내용|  
|------------|----------------|-----------|---|------------------|------------------------|  
|any|모두|모두|0|0|수정 안 됨|  
|`NULL`|모두|모두|0이 아닌 값|`EINVAL`|수정 안 됨|  
|모두|모두|`NULL`|0이 아닌 값|`EINVAL`|`dest`가 0이 됨|  
|모두|< `count`|모두|0이 아닌 값|`ERANGE`|`dest`가 0이 됨|  
  
## <a name="remarks"></a>설명  
 `memcpy_s`는 `count`에서 `src`로 `dest` 바이트를 복사하고 `wmemcpy_s`는 `count` 와이드 문자(2바이트)를 복사합니다. 소스와 대상이 겹치는 경우 `memcpy_s`의 동작이 정의되지 않습니다. `memmove_s`를 사용하면 겹치는 영역을 처리할 수 있습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `count`가 0이 아니고 `dest` 또는 `src`가 null 포인터이거나 `destSize`가 `count`보다 작은 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `EINVAL` 또는 `ERANGE`를 반환하거나 `errno`를 반환 값으로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`memcpy_s`|\<memory.h> 또는 \<string.h>|  
|`wmemcpy_s`|\<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## <a name="see-also"></a>참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)