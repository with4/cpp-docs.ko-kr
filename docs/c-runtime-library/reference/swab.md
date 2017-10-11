---
title: _swab | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: a3043abf425055d8cb21108a30db2e6382e19c1a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="swab"></a>_swab
바이트를 교환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `src`  
 복사하고 교환할 데이터입니다.  
  
 `dest`  
 교환된 데이터에 대한 저장소 위치입니다.  
  
 `n`  
 복사되고 교환될 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값
 `swab` 함수는 값을 반환하지 않습니다. `src` 또는 `dest` 포인터가 null이거나 `n`이 0보다 작으면 이 함수는 `errno`를 `EINVAL`로 설정하며, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.
 
## <a name="remarks"></a>설명  
 `n`이 짝수인 경우 `_swab` 함수는 `n`에서 `src`바이트를 복사하고, 인접한 각 바이트 쌍을 교환하고, 결과를 `dest`에 저장합니다. `n`이 홀수인 경우 `_swab`은 `src`의 첫 `n-1`바이트를 복사 및 교환하며 마지막 바이트는 복사되지 않습니다. `_swab` 함수는 일반적으로 다른 바이트 순서를 사용하는 컴퓨터에 전송할 이진 데이터를 준비하는 데 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_swab`|C: \<stdlib.h> C++: \<cstdlib> 또는 \<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)
