---
title: vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- vfwprintf_s
- _vfprintf_s_l
- vfprintf_s
- _vfwprintf_s_l
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
- _vftprintf_s
- vfwprintf_s
- vfprintf_s
dev_langs:
- C++
helpviewer_keywords:
- vfprintf_s_l function
- vfwprintf_s_l function
- vfwprintf_s function
- _vfprintf_s_l function
- _vfwprintf_s_l function
- vftprintf_s_l function
- vfprintf_s function
- _vftprintf_s_l function
- formatted text [C++]
- _vftprintf_s function
ms.assetid: eab6f563-46e2-4806-963f-2b23f339ecdc
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fa2b1f00b7da71690459b332c3121594abf475f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="vfprintfs-vfprintfsl-vfwprintfs-vfwprintfsl"></a>vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l

인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
int vfprintf_s(
   FILE *stream,
   const char *format,
   va_list argptr
);
int _vfprintf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale,
   va_list argptr
);
int vfwprintf_s(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
int _vfwprintf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*format*<br/>
형식 사양입니다.

*argptr*<br/>
인수 목록에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="return-value"></a>반환 값

**vfprintf_s** 및 **vfwprintf_s** 는 출력 오류가 발생 하는 경우 종료 null 문자 또는 음수 값을 포함 하지 않고 작성 된 문자 수를 반환 합니다. 어느 경우 *스트림* 또는 *형식* 가 null 포인터 또는에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 형식 문자열에 잘못 된 서식 문자가 들어 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수 실행을 계속 허용 된,-1을 반환 하 고 설정 **errno** 를 **EINVAL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 인수 목록에 대 한 포인터 다음 기록 하 고 형식이 지정된 된 데이터를 *스트림*합니다.

이러한 함수는 안전 하지 않은 버전만 한다는 점에서 다릅니다 안전한 버전을 확인 하 고 *형식* 유효한 서식 문자를 포함 하는 문자열입니다.

**vfwprintf_s** 의 와이드 문자 버전이 **vfprintf_s**; 스트림이 ANSI 모드에서 열리는 경우 두 함수는 동일 하 게 작동 합니다. **vfprintf_s** 현재 출력 유니코드 스트림을 지원 하지 않습니다.

있는 이러한 함수 버전은 **_l** 은 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 하는 점을 제외 하 고 접미사는 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftprintf_s**|**vfprintf_s**|**vfprintf_s**|**vfwprintf_s**|
|**_vftprintf_s_l**|**_vfprintf_s_l**|**_vfprintf_s_l**|**_vfwprintf_s_l**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**vfprintf_s**, **_vfprintf_s_l**|\<stdio.h> 및 \<stdarg.h>|\<varargs.h>*|
|**vfwprintf_s**, **_vfwprintf_s_l**|\<stdio.h> 또는 \<wchar.h> 및 \<stdarg.h>|\<varargs.h>*|

\* UNIX V 호환성을 위해 필요합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
