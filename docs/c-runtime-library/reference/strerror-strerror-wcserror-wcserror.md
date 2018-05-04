---
title: strerror, _strerror, _wcserror, __wcserror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e89a5de45baeb9b3beea2aa538cb0a2168f3c5ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror

시스템 오류 메시지 문자열을 가져옵니다 (**strerror**, **_wcserror**) 사용자가 제공한 오류 메시지 문자열의 형식을 지정 하거나 (**_strerror**, **__wcserror**). 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
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

### <a name="parameters"></a>매개 변수

*errnum*<br/>
오류 번호

*strErrMsg*<br/>
사용자 제공 메시지

## <a name="return-value"></a>반환 값

이러한 모든 함수는 오류 메시지 문자열에 대한 포인터를 반환합니다. 후속 호출 시 문자열을 덮어쓸 수 있습니다.

## <a name="remarks"></a>설명

**strerror** 지도 함수 *errnum* 오류 메시지 문자열을 문자열에 대 한 포인터를 반환 합니다. 모두 **strerror** 나 **_strerror** 실제로 메시지를 인쇄:와 같은 출력 함수를 호출 해야 하는, [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

경우 *strErrMsg* 변수로 전달 **NULL**, **_strerror** 오류를 생성 한 마지막 라이브러리 호출에 대 한 시스템 오류 메시지를 포함 하는 문자열에 대 한 포인터를 반환 합니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. 경우 *strErrMsg* 과 같지 않은 **NULL**, 다음 **_strerror** 문자열 메시지, 콜론, 공백, 시스템 오류 순서에 따라 포함 된 문자열에 대 한 포인터를 반환 합니다. 오류가 발생 하 고 줄 바꿈 문자를 생성 하는 마지막 라이브러리 호출에 대 한 메시지입니다. 문자열 메시지는 94자 이하여야 합니다.

에 대 한 실제 오류 번호 **_strerror** 변수에 저장 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 정확한 결과 생성 하려면 호출 **_strerror** 라이브러리 루틴이 오류와 함께 반환 된 후에 즉시 합니다. 그렇지 않으면 후속 호출을 **strerror** 또는 **_strerror** 덮어쓸 수는 **errno** 값입니다.

**_wcserror** 및 **__wcserror** 와이드 문자 버전의 **strerror** 및 **_strerror**각각.

**_strerror**, **_wcserror**, 및 **__wcserror** ANSI 정의의 일부가 아닌 하며 Microsoft 확장 되는 사용 하지 않는 이식 가능한 코드가 필요한 경우는 것이 좋습니다. ANSI 호환성을 위해 사용 하 여 **strerror** 대신 합니다.

오류 문자열을 가져오려면 권장 **strerror** 또는 **_wcserror** 사용 되지 않는 매크로 대신 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 사용 되지 않는 내부 함수 **__sys_errlist** 및 **__sys_nerr**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[perror](perror-wperror.md)의 예를 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
