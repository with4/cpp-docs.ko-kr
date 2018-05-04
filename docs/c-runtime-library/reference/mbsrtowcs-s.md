---
title: mbsrtowcs_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbsrtowcs_s
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
- mbsrtowcs_s
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8885d11c7fca10c63077464020a8bbab2b6f3ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="mbsrtowcss"></a>mbsrtowcs_s

현재 로캘의 멀티바이트 문자열을 와이드 문자열 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [mbsrtowcs](mbsrtowcs.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t * wcstr,
   size_t sizeInWords,
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
);
template <size_t size>
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t (&wcstr)[size],
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
변환된 문자 수입니다.

*wcstr*<br/>
결과로 생성되는 와이드 문자열을 저장할 버퍼의 주소입니다.

*sizeInWords*<br/>
크기 *wcstr* 단어 (와이드 문자)입니다.

*mbstr*<br/>
변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.

*count*<br/>
와이드 문자에 저장할 최대 수는 *wcstr* 버퍼에는 종료 null을 포함 하지 않고 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.

*mbstate*<br/>
에 대 한 포인터는 **mbstate_t** 변환 상태 개체입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 때문에 내부 **mbstate_t** 개체는 스레드로부터 안전 하지, 전달 하는 항상 고유한 것이 좋습니다 *mbstate* 매개 변수입니다.

## <a name="return-value"></a>반환 값

변환이 완료되면 0이 반환되고, 실패하면 오류 코드가 반환됩니다.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*wcstr* 가 null 포인터 및 *sizeInWords* > 0|**EINVAL**|
|*mbstr* 가 null 포인터|**EINVAL**|
|문자열 간접적으로 가리키는 여 *mbstr* 현재 로캘에 대 한 잘못 된 멀티 바이트 시퀀스를 포함 합니다.|**EILSEQ**|
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *count* 은 **_TRUNCATE**; 자세한 내용은 설명 부분 참조)|**ERANGE**|

이러한 상황 중 하나라도 발생하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 함수 실행을 계속 허용 된, 메시지가 표시 되 면 오류 코드를 반환 하 고 설정 **errno** 테이블에 표시 된 대로 합니다.

## <a name="remarks"></a>설명

**mbsrtowcs_s** 함수 직접으로 가리키는 멀티 바이트 문자의 문자열 변환 *mbstr* 가리키는 버퍼에 저장 된 와이드 문자로 *wcstr*, 만든 사람 에 포함 된 변환 상태를 사용 하 여 *mbstate*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- 멀티바이트 null 문자가 발견되는 경우

- 잘못된 멀티바이트 문자가 발견되는 경우

- 에 저장 된 와이드 문자의 수가 *wcstr* equals 버퍼링 *count*합니다.

대상 문자열 *wcstr* 은 항상 null로 끝나는, 오류 발생 시도 포함 하지 않는 한 *wcstr* 가 null 포인터입니다.

경우 *count* 는 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md), **mbsrtowcs_s** 만큼 문자열 최대한 변환 하지만 null에 대 한 대상 버퍼에 적합 합니다. 종결자입니다.

경우 **mbsrtowcs_s** 소스 문자열을 성공적으로 변환 하 고 null 종결자를 변환된 된 문자열의 와이드 문자에서 크기를 가져가서  *&#42;pReturnValue*제공  *pReturnValue* 가 null 포인터가 아닙니다. 이 경우에는 *wcstr* 인수가 null 포인터 이며 필요한 버퍼 크기를 결정할 수 있습니다. 되는 경우 *wcstr* null 포인터가 *count* 는 무시 됩니다.

경우 *wcstr* 가 null 포인터가 아닌 가리키는 포인터 개체 *mbstr* 종결 null 문자에 도달 했으므로 변환이 중지 하는 경우에 null 포인터가 할당 됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.

경우 *mbstate* 가 null 포인터 이면 라이브러리 내부 **mbstate_t** 변환 상태 정적 개체가 사용 됩니다. 이 내부 정적 개체가 스레드로부터 안전한 없기 때문에 전달 하는 고유한 것이 좋습니다 *mbstate* 값입니다.

경우 **mbsrtowcs_s** 현재 로캘에서 유효 하지 않은 멀티 바이트 문자를 발견할-1 가져가서  *&#42;pReturnValue*, 대상 버퍼를 설정 *wcstr* 빈 문자열로 설정 **errno** 를 **EILSEQ**, 반환 **EILSEQ**합니다.

시퀀스에서 가리키는 경우 *mbstr* 및 *wcstr* 겹치는 경우의 동작 **mbsrtowcs_s** 정의 되지 않습니다. **mbsrtowcs_s** 현재 로캘의 LC_TYPE 범주가 영향을 받습니다.

> [!IMPORTANT]
> 되도록 *wcstr* 및 *mbstr* 이 겹치지 않을 있는지 *개수* 올바르게 변환할 멀티 바이트 문자 수를 반영 합니다.

**mbsrtowcs_s** 함수에서와 다른 [mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md) 다시 시작할 합니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어, 응용 프로그램 사용 해야 **mbsrlen** 대신 **mbslen**후속 호출 하는 경우, **mbsrtowcs_s** 대신 사용 됩니다 **mbstowcs_s**.

C++에서는 템플릿 오버로드로 이러한 함수를 간편하게 사용할 수 있습니다. 즉, 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 또한 기존의 비보안 함수를 그에 해당하는 안전한 최신 함수로 자동 교체할 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**mbsrtowcs_s** 함수는 현재 스레드 호출 함수 아니면 다중 스레드로부터 안전은 **setlocale** 이 함수가 실행 중 상태로 및 *mbstate* 인수는 null 포인터가 아닙니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
