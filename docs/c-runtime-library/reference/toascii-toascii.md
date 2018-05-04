---
title: toascii, __toascii | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __toascii
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
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
dev_langs:
- C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead516a7e298e56d13d8f1a09a054057796ca64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="toascii-toascii"></a>toascii, __toascii

잘라내기를 통해 문자를 7비트 ASCII로 변환합니다.

## <a name="syntax"></a>구문

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>매개 변수

*c*<br/>
변환할 문자입니다.

## <a name="return-value"></a>반환 값

**__toascii** 값을 변환 *c* 7 비트 ascii 범위 및 결과 반환 합니다. 오류를 나타내기 위해 예약된 반환 값은 없습니다.

## <a name="remarks"></a>설명

**__toascii** 루틴 하위 7 비트를 잘라 지정 된 문자를 ASCII 문자로 변환 합니다. 다른 변환은 적용되지 않습니다.

**__toascii** 전처리기 매크로 _CTYPE_DISABLE_MACROS 정의 되어 있지 않으면 루틴은 매크로로 정의 합니다. 이전 버전과 호환성에 대 한 **toascii** 매크로로 정의 된 경우에만 [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) 이 정의 되지 않았거나; 0으로 정의한 그렇지 않으면 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**toascii**, **__toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> 또는 \<ctype.h>|

**toascii** 매크로 POSIX 확장 및 **__toascii** POSIX 확장의 Microsoft 관련 구현입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[to 함수](../../c-runtime-library/to-functions.md)<br/>
