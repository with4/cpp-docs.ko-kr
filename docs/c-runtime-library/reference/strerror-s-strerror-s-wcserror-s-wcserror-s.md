---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
dev_langs:
- C++
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 21
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
ms.openlocfilehash: 70875568a8f77f9e4039e69dadbe9daf3c1c5e01
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s
시스템 오류 메시지(`strerror_s`, `_wcserror_s`)를 가져오거나, 사용자가 제공한 오류 메시지(`_strerror_s`, `__wcserror_s`)를 출력합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 오류 문자열을 저장할 버퍼입니다.  
  
 `numberOfElements`  
 버퍼의 크기입니다.  
  
 `errnum`  
 오류 번호  
  
 `strErrMsg`  
 사용자 제공 메시지  
  
## <a name="return-value"></a>반환 값  
 성공시 0, 실패시 오류 코드.  
  
### <a name="error-condtions"></a>오류 조건  
  
|`buffer`|`numberOfElements`|`strErrMsg`|`buffer`의 내용|  
|--------------|------------------------|-----------------|--------------------------|  
|`NULL`|any|any|해당 없음|  
|any|0|any|수정 안 됨|  
  
## <a name="remarks"></a>설명  
 `strerror_s` 함수는 `errnum`을 오류 메시지 문자열로 매핑하고 `buffer`에서 해당 문자열을 반환합니다. `_strerror_s`는 오류 번호를 사용하지 않으며 `errno`의 현재 값을 사용하여 적절한 메시지를 결정합니다. `strerror_s` 및 `_strerror_s` 둘 다 실제로 메시지를 출력하지는 않습니다. 따라서 [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)와 같은 출력 함수를 호출해야 합니다.  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 `strErrMsg`가 `NULL`이면 `_strerror_s`는 오류를 발생시킨 마지막 라이브러리 호출에 대한 시스템 오류 메시지가 포함된 문자열을 `buffer`에서 반환합니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. `strErrMsg`가 `NULL`과 같지 않으면 `_strerror_s`는 문자열 메시지, 콜론, 공백, 오류가 발생한 마지막 라이브러리 호출에 대한 시스템 오류 메시지 및 줄 바꿈 문자가 순서대로 포함된 문자열을 `buffer`에서 반환합니다. 문자열 메시지는 94자 이하여야 합니다.  
  
 길이가 `numberOfElements` -1을 초과하는 경우 이러한 함수는 오류 메시지를 자릅니다. `buffer`의 결과 문자열은 항상 null로 종료됩니다.  
  
 `_strerror_s`의 실제 오류 번호는 변수 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)에 저장됩니다. [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 시스템 오류 메시지에 액세스합니다. 이 변수는 오류 번호순으로 정렬된 메시지 배열입니다. `_strerror_s`는 `errno` 값을 변수 `_sys_errlist`에 대한 인덱스로 사용하여 적합한 오류 메시지에 액세스합니다. [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수의 값은 `_sys_errlist` 배열에 있는 요소의 최대 수로 정의됩니다. 정확한 결과를 생성하려면 라이브러리 루틴이 오류와 함께 반환될 때 바로 `_strerror_s`을 호출합니다. 그렇지 않으면 `strerror_s` 또는 `_strerror_s`에 대한 후속 호출이 `errno` 값을 덮어쓸 수 있습니다.  
  
 `_wcserror_s` 및 `__wcserror_s`은 각각 `strerror_s` 및 `_strerror_s`의 와이드 문자 버전입니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 버퍼가 `NULL`이거나 size 매개 변수가 0이면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 `EINVAL`을 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
 `_strerror_s``_wcserror_s`, 및 `__wcserror_s` ANSI 정의의 일부가 아닌 않는 대신에 대 한 Microsoft 확장입니다. 이식성이 필요한 경우에는 이러한 함수를 사용하지 마세요. ANSI 호환성이 필요한 경우에는 `strerror_s`를 대신 사용하세요.  
  
 C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`strerror_s`, `_strerror_s`|\<string.h>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [perror](../../c-runtime-library/reference/perror-wperror.md)의 예를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
