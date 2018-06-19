---
title: _ismbbkprint, _ismbbkprint_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ismbbkprint
- _ismbbkprint_l
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
- _ismbbkprint_l
- ismbbkprint
- _ismbbkprint
- ismbbkprint_l
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkprint function
- ismbbkprint_l function
- ismbbkprint function
- _ismbbkprint_l function
ms.assetid: 8d1d3258-1e34-4365-81ed-97c95de25475
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1a6a215bac14f81d29d83a856313133fb4e88a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399503"
---
# <a name="ismbbkprint-ismbbkprintl"></a>_ismbbkprint, _ismbbkprint_l

특정 멀티바이트 문자가 문장 부호 기호인지 여부를 결정합니다.

## <a name="syntax"></a>구문

```C
int _ismbbkprint(
   unsigned int c
);
int _ismbbkprint_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_ismbbkprint** 경우 0이 아닌 값을 반환 하는 정수 *c* 은 ASCII가 아닌 텍스트 또는 ASCII가 아닌 문장 부호인 0 없는 경우. 예를 들어 **_ismbbkprint**는 932 코드 페이지에서만 가타카나 영숫자 또는 가타카나 문장 부호를 테스트합니다(범위: 0xA1 – 0xDF). **_ismbbkprint** 로캘 종속 문자 설정에 대 한 현재 로캘을 사용 합니다. **_ismbbkprint_l** 전달 된 로캘을 사용 하 여 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_ismbbkprint**|\<mbctype.h>|
|**_ismbbkprint_l**|\<mbctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
