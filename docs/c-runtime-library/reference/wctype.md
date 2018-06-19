---
title: wctype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wctype
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
- wctype
dev_langs:
- C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb5003db02ed27c2906ebc3619313489e40e5fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411902"
---
# <a name="wctype"></a>wctype

와이드 문자 코드에 대한 분류 규칙을 결정합니다.

## <a name="syntax"></a>구문

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>매개 변수

*속성*<br/>
속성 문자열입니다.

## <a name="return-value"></a>반환 값

경우는 **LC_CTYPE** 현재 로캘의 범주가 이름이 속성 문자열을 일치 하는 분류 규칙을 정의 하지 않습니다 *속성*, 함수가 0을 반환 합니다. 그렇지 않으면 이 함수는 [towctrans](towctrans.md)에 대한 후속 호출에 두 번째 인수로 사용할 수 있는 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

이 함수는 와이드 문자 코드에 대한 분류 규칙을 결정합니다. 다음 호출 쌍은 모든 로캘에서 동일하게 동작하지만 구현은 "C" 로캘에서도 추가 분류 규칙을 정의할 수 있습니다.

|함수|다음과 같이 사용|
|--------------|-------------|
|iswalnum(c)|iswctype (c, wctype ("alnum 과"))|
|iswalpha(c)|iswctype (c, wctype ("알파"))|
|iswcntrl(c)|iswctype (c, wctype ("cntrl"))|
|iswdigit(c)|iswctype (c, wctype ("자리"))|
|iswgraph(c)|iswctype (c, wctype ("그래프"))|
|iswlower(c)|iswctype (c, wctype ("낮음"))|
|iswprint(c)|iswctype (c, wctype ("print"))|
|iswpunct(c)|iswctype (c, wctype ("좁 힘"))|
|iswspace(c)|iswctype (c, wctype ("공간"))|
|iswupper(c)|iswctype (c, wctype ("위쪽"))|
|iswxdigit(c)|iswctype (c, wctype ("xdigit"))|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
