---
title: _mbccpy_s, _mbccpy_s_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs:
- C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a52314209b62c818623e315757dcd358ec491
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404030"
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l

한 문자열에서 다른 문자열로 멀티바이트 문자를 복사합니다. 이러한 버전의 [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
복사 대상입니다.

*buffSizeInBytes*<br/>
대상 버퍼의 크기입니다.

*pCopied*<br/>
복사된 바이트 수로 채워집니다(성공할 경우 1 또는 2). 전달 **NULL** 수에 대 한 중요 하지 않은 경우.

*src*<br/>
복사할 멀티바이트 문자입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다. 경우 *src* 또는 *dest* 은 **NULL**, 둘 이상의 또는 **buffSizeinBytes** 에 바이트를 복사 합니다 *dest*, 다음에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우 함수는 반환 **EINVAL** 및 **errno** 로 설정 된 **EINVAL**합니다.

## <a name="remarks"></a>설명

**_mbccpy_s** 함수에서 하나의 멀티 바이트 문자를 복사 *src* 를 *dest*합니다. 경우 *src* 암시적으로 호출에 의해 결정 된 멀티 바이트 문자의 선행 바이트를 가리키지 않습니다 [_ismbblead](ismbblead-ismbblead-l.md), 단일 바이트 다음 하 *src* 가리키는 복사 됩니다. 경우 *src* 지점 뒤에 오는 바이트가 선행 바이트를 0 이며 따라서 잘못 된 다음 0 복사할 *dest*, **errno** 로 설정 되어 **EILSEQ**, 및 함수에서 반환 **EILSEQ**합니다.

**_mbccpy_s** null 종결자를 추가 하지 않습니다; 그러나 경우 *src* 해당 null 복사 않습니다 null 문자를 가리키는 *dest* (이 단일 바이트 복사본이 일반).

값 *pCopied* 로 복사 된 바이트 수입니다. 연산이 성공할 경우 가능한 값은 1과 2입니다. 경우 **NULL** 전달 되며,이 매개 변수가 무시 됩니다.

|*src*|복사할 *dest*|*pCopied*|반환 값|
|-----------|----------------------|---------------|------------------|
|비선행 바이트|비선행 바이트|1|0|
|0|0|1|0|
|선행 바이트와 그 뒤의 0이 아닌 값|선행 바이트와 그 뒤의 0이 아닌 값|2|0|
|선행 바이트와 그 뒤의 0|0|1|**EILSEQ**|

두 번째 행은 첫 번째 행의 특수 사례일 뿐입니다. 또한 테이블 가정 하는 참고 *buffSizeInBytes* >= *pCopied*합니다.

**_mbccpy_s** 모든 로캘 종속 동작에 대해 현재 로캘을 사용 합니다. **_mbccpy_s_l** 동일 **_mbccpy_s** 점을 제외 하 고 **_mbccpy_s_l** 모든 로캘 종속 동작에 대해 전달 된 로캘을 사용 합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|매크로 또는 인라인 함수에 매핑됩니다.|**_mbccpy_s**|매크로 또는 인라인 함수에 매핑됩니다.|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
