---
title: memcpy_s, wmemcpy_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12bf97e596a7cb4e3befa4c0633a8ef2df29a6d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s

버퍼 간에 바이트를 복사합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [memcpy, wmemcpy](memcpy-wmemcpy.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
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

### <a name="parameters"></a>매개 변수

*dest*<br/>
새 버퍼입니다.

*destSize*<br/>
대상 버퍼의 크기로, memcpy_s의 경우 바이트 단위이고 wmemcpy_s의 경우 와이드 문자(wchar_t) 단위입니다.

*src*<br/>
복사할 버퍼입니다.

*count*<br/>
복사할 문자 수입니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*dest*|*destSize*|*src*|*count*|반환 값|내용을 *dest*|
|------------|----------------|-----------|---|------------------|------------------------|
|모두|모두|모두|0|0|수정 안 됨|
|**NULL**|모두|모두|0이 아닌 값|**EINVAL**|수정 안 됨|
|모두|모두|**NULL**|0이 아닌 값|**EINVAL**|*dest* 0|
|모두|< *개수*|모두|0이 아닌 값|**ERANGE**|*dest* 0|

## <a name="remarks"></a>설명

**memcpy_s** 복사본 *count* 바이트 *src* 를 *dest*; **wmemcpy_s** 복사본 *count* 와이드 문자 (2 바이트)입니다. 소스와 대상이 겹치는 경우의 동작 **memcpy_s** 정의 되지 않습니다. 사용 하 여 **memmove_s** 하면 겹치는 영역을 처리 하도록 합니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 *count* 0이 아닌 및 *dest* 또는 *src* 가 null 포인터 또는 *destSize* 보다 작으면 *count*에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는이 함수를 이러한 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우 이러한 함수가 반환 **EINVAL** 또는 **ERANGE** 설정 **errno** 반환 값입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> 또는 \<string.h>|
|**wmemcpy_s**|\<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
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

## <a name="see-also"></a>참고자료

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
