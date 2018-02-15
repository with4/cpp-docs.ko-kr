---
title: strerror, _strerror, _wcserror, __wcserror | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs:
- C++
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85fee7ce2b3c4264e8593082640489aae01cb9e0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror
시스템 오류 메시지 문자열을 얻거나(`strerror`, `_wcserror`) 사용자가 제공하는 오류 메시지 문자열의 형식을 지정합니다(`_strerror`, `__wcserror`). 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *strerror(  
   int errnum   
);  
char *_strerror(  
   const char *strErrMsg   
);  
wchar_t * _wcserror(  
   int errnum   
);  
wchar_t * __wcserror(  
   const wchar_t *strErrMsg   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `errnum`  
 오류 번호  
  
 `strErrMsg`  
 사용자 제공 메시지  
  
## <a name="return-value"></a>반환 값  
 이러한 모든 함수는 오류 메시지 문자열에 대한 포인터를 반환합니다. 후속 호출 시 문자열을 덮어쓸 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `strerror` 함수는 `errnum`을 오류 메시지 문자열로 매핑하고 해당 문자열에 대한 포인터를 반환합니다. `strerror` 및 `_strerror` 둘 다 실제로 메시지를 출력하지는 않습니다. 따라서 [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)와 같은 출력 함수를 호출해야 합니다.  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 `strErrMsg`가 `NULL`로 전달되면 `_strerror`는 오류를 발생시킨 마지막 라이브러리 호출에 대한 시스템 오류 메시지가 포함된 문자열을 가리키는 포인터를 반환합니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. `strErrMsg`가 `NULL`과 같지 않으면 `_strerror`은 문자열 메시지, 콜론, 공백, 오류가 발생한 마지막 라이브러리 호출에 대한 시스템 오류 메시지 및 줄 바꿈 문자가 순서대로 포함된 문자열에 대한 포인터를 반환합니다. 문자열 메시지는 94자 이하여야 합니다.  
  
 `_strerror`의 실제 오류 번호는 변수 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)에 저장됩니다. 정확한 결과를 생성하려면 라이브러리 루틴이 오류와 함께 반환될 때 바로 `_strerror`을 호출합니다. 그렇지 않으면 `strerror` 또는 `_strerror`에 대한 후속 호출이 `errno` 값을 덮어쓸 수 있습니다.  
  
 `_wcserror` 및 `__wcserror`은 각각 `strerror` 및 `_strerror`의 와이드 문자 버전입니다.  
  
 `_strerror`, `_wcserror` 및 `__wcserror`은 ANSI 정의의 일부가 아닙니다. 이러한 함수는 Microsoft 확장으로 이식 가능한 코드가 필요한 경우에는 사용하지 않는 것이 좋습니다. ANSI 호환성을 위해 대신 `strerror`을 사용하세요.  
  
 오류 문자열을 가져오려면 사용되지 않는 매크로 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)과 사용되지 않는 내부 함수 `__sys_errlist` 및 `__sys_nerr` 대신 `strerror` 또는 `_wcserror`를 사용하는 것이 좋습니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`strerror`|\<string.h>|  
|`_strerror`|\<string.h>|  
|`_wcserror`, `__wcserror`|\<string.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [perror](../../c-runtime-library/reference/perror-wperror.md)의 예를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)