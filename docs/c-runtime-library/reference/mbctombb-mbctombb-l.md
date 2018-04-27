---
title: _mbctombb, _mbctombb_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbctombb_l
- _mbctombb
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
- _mbctombb_l
- _mbctombb
- mbctombb_l
- mbctombb
dev_langs:
- C++
helpviewer_keywords:
- _mbctombb function
- mbctombb_l function
- mbctombb function
- _mbctombb_l function
ms.assetid: d90970b8-71ff-4586-b6a2-f9ceb811f776
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45567a2486a0783cd4b1f82e5a81046e529c49df
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="mbctombb-mbctombbl"></a>_mbctombb, _mbctombb_l

더블바이트 멀티바이트 문자를 해당 싱글바이트 멀티바이트 문자로 변환합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
unsigned int _mbctombb(
   unsigned int c
);
unsigned int _mbctombb_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
변환할 멀티바이트 문자입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공 하면 **_mbctombb** 및 **_mbctombb_l** 에 해당 하는 단일 바이트 문자를 반환 *c*; 그렇지 않으면 반환 *c* .

## <a name="remarks"></a>설명

**_mbctombb** 및 **_mbctombb_l** 함수는 주어진된 멀티 바이트 문자를 해당 싱글바이트 멀티 바이트 문자로 변환 합니다. 문자 변환 될 0xDF 범위 0x20-0x7E 또는 0xA1-내의 단일 바이트 문자를 일치 해야 합니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale](setlocale-wsetlocale.md) 자세한 정보에 대 한 합니다. 없이이 함수의 버전은 **_l** 접미사가 로캘 종속 동작에 대 한 현재 로캘을 사용 하 여 버전으로는 **_l** 제외 하 고 전달 된 로캘 매개 변수를 사용 하 여 접미사는 동일 대신 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이전 버전에서는 **_mbctombb** 호출한 **zentohan**합니다. 사용 하 여 **_mbctombb** 대신 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_mbctombb**|\<mbstring.h>|
|**_mbctombb_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[_mbbtombc, _mbbtombc_l](mbbtombc-mbbtombc-l.md)<br/>
[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)<br/>
[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)<br/>
