---
title: _swab | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _swab
- stdlib/_swab
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
dev_langs:
- C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeedb217466262d8643a851b5f93cb9ac26fb0a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408448"
---
# <a name="swab"></a>_swab

바이트를 교환합니다.

## <a name="syntax"></a>구문

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>매개 변수

*src* 데이터를 복사 하 고 교환 합니다.

*dest* 교환 된 데이터에 대 한 저장소 위치입니다.

*n* 바이트 복사 하 고 교환할 수입니다.

## <a name="return-value"></a>반환 값

**swab** 함수 값을 반환 하지 않습니다. 함수 집합 **errno** 를 **EINVAL** 경우는 *src* 또는 *dest* 포인터가 null이 또는 *n* 작습니다 0이 고 잘못 된 매개 변수 보다 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

경우 *n* ,는 **_swab** 복사본 함수 *n* 바이트 *src*, 인접 한 바이트의 각 쌍을 교환 하 고 에서결과저장*dest*합니다. 경우 *n* 홀수 이면 **_swab** 복사 하 고 첫 번째 교환 *n*-1 바이트의 *src*, 마지막 바이트 복사 되지 않습니다. **_swab** 함수는 일반적으로 다른 바이트 순서를 사용 하는 컴퓨터에 전송할 이진 데이터를 준비 하는 데 사용 됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>참고자료

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
