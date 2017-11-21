---
title: "memcpy, wmemcpy | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy
- wmemcpy
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
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
dev_langs: C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 38c00e7d7c5eb9f4a1076ae3814c17a8062fe322
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy
버퍼 간에 바이트를 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [memcpy_s, wmemcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void *memcpy(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemcpy(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dest`  
 새 버퍼입니다.  
  
 `src`  
 복사할 버퍼입니다.  
  
 `count`  
 복사할 문자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 `dest`의 값  
  
## <a name="remarks"></a>설명  
 `memcpy`는 `count`에서 `src`로 `dest` 바이트를 복사하고 `wmemcpy`는 `count` 와이드 문자(2바이트)를 복사합니다. 소스와 대상이 겹치는 경우 `memcpy`의 동작이 정의되지 않습니다. `memmove`를 사용하면 겹치는 영역을 처리할 수 있습니다.  
  
> [!IMPORTANT]
>  대상 버퍼의 크기가 소스 버퍼의 크기보다 크거나 같아야 합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
> [!IMPORTANT]
>  `memcpy`의 부적합한 사용으로 인해 매우 많은 버퍼 오버런과 보안 악용 가능성이 추적되었으므로 이 함수는 SDL(Security Development Lifecycle)에 의해 "금지" 항목으로 분류되었습니다.  일부 VC++ 라이브러리 클래스는 `memcpy`를 계속 사용할 수 있습니다.  또한 VC++ 컴파일러 최적화 프로그램에서 `memcpy`에 대한 호출을 내보내는 경우도 있습니다.  Visual C++ 제품은 SDL 프로세스에 따라 개발되었으므로 이처럼 금지된 함수의 사용이 철저하게 평가되었습니다.  라이브러리에서 이러한 함수를 사용하는 경우에는 이러한 호출을 통해 버퍼 오버런이 허용되지 않도록 호출을 면밀하게 검사했습니다.  컴파일러의 경우 특정 코드 패턴이 `memcpy`의 패턴과 동일한 것으로 인식되어 함수 호출로 바뀌는 경우가 있습니다.  이러한 경우에는 `memcpy`를 사용해도 원래 지침처럼 위험하지 않습니다. 이러한 패턴은 성능이 조정된 `memcpy` 함수에 대한 호출로 최적화되었을 뿐이기 때문입니다.  "안전한" CRT 함수를 사용한다고 해서 보안이 보장되는 것은 아니듯이(위험 가능성만 낮아질 뿐임), "금지된" 함수를 사용한다고 해서 반드시 위험한 것도 아니며 보안을 유지하려면 더욱 철저한 확인이 필요할 뿐입니다.  
>   
>  VC++ 컴파일러 및 라이브러리의 `memcpy` 사용은 매우 철저하게 확인되었으므로 일반적으로 SDL과 호환되는 코드 내에서도 이러한 호출이 허용됩니다.  응용 프로그램 소스 코드에 포함된 `memcpy` 호출은 보안 전문가가 해당 사용을 검토한 경우에만 SDL과 호환됩니다.  
  
 `memcpy` 상수가 아래 예제처럼 함수를 사용하지 않기 위해 포함 문 이전에 정의되는 경우에만 `wmemcpy` 및 `_CRT_SECURE_DEPRECATE_MEMORY` 함수가 사용되지 않습니다.  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <memory.h>  
```  
  
 또는  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`memcpy`|\<memory.h> 또는 \<string.h>|  
|`wmemcpy`|\<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 `memcpy`를 사용하는 방법에 대한 샘플은 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)