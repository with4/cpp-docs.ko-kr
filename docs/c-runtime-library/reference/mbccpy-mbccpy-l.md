---
title: _mbccpy, _mbccpy_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbccpy
- _mbccpy_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
dev_langs:
- C++
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 583f241d85c3c94a2f276e39c187baf175c5a1f4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="mbccpy-mbccpyl"></a>_mbccpy, _mbccpy_l

한 문자열에서 다른 문자열로 멀티바이트 문자를 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md)을 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _mbccpy(
   unsigned char *dest,
   const unsigned char *src
);
void _mbccpy_l(
   unsigned char *dest,
   const unsigned char *src,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*dest* 복사 대상입니다.

*src* 복사할 멀티 바이트 문자입니다.

*로캘* 사용할 로캘입니다.

## <a name="remarks"></a>설명

**_mbccpy** 함수에서 하나의 멀티 바이트 문자를 복사 *src* 를 *dest*합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 **_mbccpy** null 포인터에 대 한 전달 *dest* 또는 *src*에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md). 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL**합니다.

**_mbccpy** 모든 로캘 종속 동작에 대해 현재 로캘을 사용 합니다. **_mbccpy_l** 동일 **_mbccpy** 점을 제외 하 고 **_mbccpy_l** 모든 로캘 종속 동작에 대해 전달 된 로캘을 사용 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**보안 정보** null로 끝나는 문자열을 사용하세요. null로 끝나는 문자열은 대상 버퍼의 크기를 초과할 수 없습니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요. 버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|매크로 또는 인라인 함수에 매핑|**_mbccpy**|매크로 또는 인라인 함수에 매핑|
|**_tccpy_l**|N/A|**_mbccpy_l**|N/A|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
