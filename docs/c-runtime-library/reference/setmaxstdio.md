---
title: _setmaxstdio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7947bb8de34b5e80321ddacf03e4606a53b5dc90
ms.lasthandoff: 02/24/2017

---
# <a name="setmaxstdio"></a>_setmaxstdio
`stdio` 수준에서 동시에 열리는 파일 수의 최대값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `newmax`  
 `stdio` 수준에서 동시에 열리는 파일 수의 새 최대값입니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되면 `newmax`를 반환하고 그렇지 않으면 -1을 반환합니다.  
  
 `newmax`가 `_IOB_ENTRIES`보다 작거나 운영 체제에서 사용 가능한 최대 핸들 수보다 많으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_setmaxstdio` 함수는 `stdio` 수준에서 동시에 열 수 있는 파일 수의 최대값을 변경합니다.  
  
 C 런타임 I/O는 이제 이전 버전에 비해 Win32 플랫폼에서 훨씬 더 많은 파일을 열 수 있도록 지원합니다. [lowio 수준](../../c-runtime-library/low-level-i-o.md)에서는 최대 2,048개의 파일을 동시에 열 수 있습니다. 즉, `_open`, `_read`, `_write` 등의 I/O 함수 패밀리를 통해 이 수만큼의 파일을 열고 액세스할 수 있습니다. [stdio 수준](../../c-runtime-library/stream-i-o.md)에서는 최대 512개의 파일을 동시에 열 수 있습니다. 즉, `fopen`, `fgetc`, `fputc` 등의 함수 패밀리를 통해 이 수만큼의 파일을 열고 액세스할 수 있습니다. `_setmaxstdio` 함수를 사용하면 `stdio` 수준에서 열 수 있는 파일 수에 대한 제한(512개)을 최대 2,048개까지 늘릴 수 있습니다.  
  
 `fopen`과 같은 `stdio` 수준 함수는 `lowio` 함수를 기반으로 작성되므로 최대값 2,048은 C 런타임 라이브러리를 통해 액세스하는 동시에 열 수 있는 파일 수에 대한 하드 상한입니다.  
  
> [!NOTE]
>  이 상한은 특정 Win32 플랫폼 및 구성에서 지원하는 수를 초과할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 `_setmaxstdio`를 사용하는 예제는 [_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md)를 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)
