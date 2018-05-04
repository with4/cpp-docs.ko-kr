---
title: _strdate_s, _wstrdate_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strdate_s
- _wstrdate_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
dev_langs:
- C++
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e4e9ff3783fc7a89e7af42ebf283209c034c0d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s

현재 시스템 날짜를 버퍼에 복사합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_strdate, _wstrdate](strdate-wstrdate.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _strdate_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strdate_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrdate_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
형식이 지정된 날짜 문자를 입력할 버퍼에 대한 포인터입니다.

*numberOfElements*<br/>
버퍼의 크기입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 ERRNO.H에 정의됩니다. 이 함수가 생성하는 정확한 오류는 아래 표를 참조하세요. 오류 코드에 대한 자세한 내용은 [errno](../../c-runtime-library/errno-constants.md)를 참조하세요.

## <a name="error-conditions"></a>오류 조건

|*buffer*|*numberOfElements*|반환|내용을 *버퍼*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(임의)|**EINVAL**|수정 안 됨|
|하지 **NULL** (유효한 버퍼 가리킴)|0|**EINVAL**|수정 안 됨|
|하지 **NULL** (유효한 버퍼 가리킴)|0 < *numberOfElements* < 9|**EINVAL**|빈 문자열|
|하지 **NULL** (유효한 버퍼 가리킴)|*numberOfElements* > = 9|0|설명에 지정된 형식의 현재 날짜|

## <a name="security-issues"></a>보안 문제

잘못 된 비 전달 **NULL** 경우 버퍼 액세스 위반이 발생에 대 한 값의 *numberOfElements* 매개 변수는 9 보다 큰 합니다.

실제 크기 보다 크면 크기에 대 한 값을 전달는 *버퍼* 버퍼 오버런이 발생 합니다.

## <a name="remarks"></a>설명

이러한 함수의 더 안전한 버전을 제공 **_strdate** 및 **_wstrdate**합니다. **_strdate_s** 함수는 현재 시스템 날짜를 가리키는 버퍼에 복사 *버퍼*포맷 된 **mm**/**dd** / **yy**여기서 **mm** 는 월을 나타내는 두 자리 숫자로 **dd** 는 날짜를 나타내는 두 자리 숫자로 및 **yy**  은 해당 연도의 마지막 두 자리 숫자입니다. 예를 들어 문자열 **12/05/99** 1999 년 12 월 5 일을 나타냅니다. 버퍼의 길이는 9자 이상이어야 합니다.

**_wstrdate_s** 의 와이드 문자 버전이 **_strdate_s**; 인수 및 반환 값의 **_wstrdate_s** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

경우 *버퍼* 는 **NULL** 포인터 또는 *numberOfElements* 보다 작거나 9 자에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된, 하는 경우 이러한 함수가-1을 반환 하 고 설정 **errno** 를 **EINVAL** 버퍼가 **NULL** 경우 *numberOfElements*가 0 또는 집합을 보다 작거나 같으면 **errno** 를 **ERANGE** 경우 *numberOfElements* 9 보다 작으면 합니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mapping"></a>제네릭 텍스트 루틴 매핑:

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> 또는 \<wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>예제

[time](time-time32-time64.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
