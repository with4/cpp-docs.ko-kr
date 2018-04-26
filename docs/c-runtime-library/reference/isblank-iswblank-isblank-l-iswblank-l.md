---
title: isblank, iswblank, _isblank_l, _iswblank_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs:
- C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dbf3c55f6a9665d8d6ad046dba653b362d46cd2a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l

정수가 공백 문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

이러한 루틴 0이 아닌 경우 반환 각 *c* 공백이 나 가로 탭 문자의 특정 표현인 또는 로캘별 텍스트 한 줄 내에서 단어를 구분 하는 데 사용 되는 문자 집합 중 하나입니다. **isblank** 경우 0이 아닌 값을 반환 *c* 는 공백 문자 (0x20) 또는 가로 탭 문자 (0x09). 에 대 한 테스트 조건의 결과 **isblank** 함수에 따라 달라 집니다는 **LC_CTYPE** 범주 참조 로캘의 자세한 정보에 대 한 설정을 [setlocale, _wsetlocale](setlocale-wsetlocale.md). 가 없는 이러한 함수 버전은 **_l** 모든 로캘 종속 동작에 대해 현재 로캘 접미사 사용 하 고, 않은 버전은 **_l** 접미사를 사용 하는 점을 제외 하 고 동일는 대신에 전달 되는 로캘. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**iswblank** 경우 0이 아닌 값을 반환 *c* 가로 탭 문자 또는 표준 공간에 해당 하는 와이드 문자입니다.

동작은 **isblank** 및 **_isblank_l** 경우 정의 되지 않습니다 *c* 가 EOF가 또는 0-0xFF 까지의 범위에 있습니다. CRT 디버그 라이브러리 사용 되는 경우 및 *c* 함수 생성에서는 이러한 값 중 하나가 아닙니다 한 어설션입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**isblank**|\<ctype.h>|
|**iswblank**|\<ctype.h> 또는 \<wchar.h>|
|**_isblank_l**|\<ctype.h>|
|**_iswblank_l**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
