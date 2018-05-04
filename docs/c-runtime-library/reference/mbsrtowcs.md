---
title: mbsrtowcs | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbsrtowcs
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsrtowcs
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb5bda16238888905678ffb3b6de01b93555ad0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="mbsrtowcs"></a>mbsrtowcs

현재 로캘의 멀티바이트 문자열을 해당하는 와이드 문자열로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [mbsrtowcs_s](mbsrtowcs-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*wcstr*<br/>
변환된 결과 와이드 문자열을 저장하는 주소입니다.

*mbstr*<br/>
변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.

*count*<br/>
문자 (바이트 아님)으로 변환 하 고에 저장할 최대 *wcstr*합니다.

*mbstate*<br/>
에 대 한 포인터는 **mbstate_t** 변환 상태 개체입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 때문에 내부 **mbstate_t** 개체는 스레드로부터 안전 하지, 전달 하는 항상 고유한 것이 좋습니다 *mbstate* 매개 변수입니다.

## <a name="return-value"></a>반환 값

종결 null 문자(있는 경우)를 포함하지 않고 정상적으로 변환된 문자 수를 반환합니다. 반환 (오류가 발생 하 고 설정 하는 경우 size_t)(-1) **errno** 를 eilseq로 설정 합니다.

## <a name="remarks"></a>설명

**mbsrtowcs** 함수 직접으로 가리키는 멀티 바이트 문자의 문자열 변환 *mbstr*를 가리키는 버퍼에 저장 된 와이드 문자로 *wcstr*, 만든 사람 에 포함 된 변환 상태를 사용 하 여 *mbstate*합니다. 변환이 계속 각 문자에 대 한 종결 null 멀티 바이트 문자 발견 될 때까지 현재 로캘에서 올바른 문자에 해당 하지 않는 멀티 바이트 시퀀스가 발생 하는 때까지 또는 *count* 문자 변환 되었습니다. 경우 **mbsrtowcs** 전이나 경우 멀티 바이트 null 문자 ('\0')에서 발생 *count* 발생 시작과 끝 16 비트 종결 null 문자를 변환 합니다.

따라서, 와이드 문자열은 *wcstr* 은 null로 끝나는 경우에 **mbsrtowcs** 멀티 바이트 null 문자를 변환 하는 동안 발생 합니다. 시퀀스에서 가리키는 경우 *mbstr* 및 *wcstr* 겹치는 경우의 동작 **mbsrtowcs** 정의 되지 않습니다. **mbsrtowcs** 현재 로캘의 LC_TYPE 범주가 영향을 받습니다.

**mbsrtowcs** 함수에서와 다른 [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) 다시 시작할 합니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, 응용 프로그램 사용 해야 **mbsrlen** 대신 **mbslen**후속 호출 하는 경우, **mbsrtowcs** 대신 사용 됩니다 **mbstowcs**.

경우 *wcstr* 가 null 포인터가 아닌 가리키는 포인터 개체 *mbstr* 종결 null 문자에 도달 했으므로 변환이 중지 하는 경우에 null 포인터가 할당 됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.

경우는 *wcstr* 인수는 null 포인터는 *count* 인수는 무시 됩니다 및 **mbsrtowcs** 와이드 문자 대상 문자열에 대해 필요한 크기를 반환 합니다. 경우 *mbstate* 가 null 포인터 이면 함수는 스레드로부터 안전 하지 않은 정적 내부 사용 **mbstate_t** 변환 상태 개체입니다. 경우 문자 시퀀스 *mbstr* 해당 멀티 바이트 없는 문자 표현이-1 반환 및 **errno** 로 설정 되어 **EILSEQ**합니다.

경우 *mbstr* 에 설명 된 대로 null 포인터인 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 하 고-1을 반환 합니다.

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**mbsrtowcs** 함수는 현재 스레드의 호출 함수는 아니면 다중 스레드로부터 안전 **setlocale** 이 함수가 실행 중 상태로 및 *mbstate* 인수가 null 포인터가 아닙니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
