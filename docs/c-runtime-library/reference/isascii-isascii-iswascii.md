---
title: isascii, __isascii, iswascii | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- iswascii
- __isascii
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
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs:
- C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4876ad6e206894fb55c3f4279e80bd55886d415d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

특정 문자가 ASCII 문자인지 여부를 결정합니다.

## <a name="syntax"></a>구문

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

## <a name="return-value"></a>반환 값

이러한 루틴 0이 아닌 경우 반환의 각 **c** ASCII 문자의 특정 표현입니다. **__isascii** 경우 0이 아닌 값을 반환 **c** 은 ASCII 문자 (0x00-0x7F 범위의)에 있습니다. **iswascii** 경우 0이 아닌 값을 반환 **c** ASCII 문자의 와이드 문자 표현입니다. 이러한 각 루틴 0을 반환 **c** 테스트 조건을 만족 하지 않습니다.

## <a name="remarks"></a>설명

둘 다 **__isascii** 및 **iswascii** 전처리기 매크로 _CTYPE_DISABLE_MACROS 정의 되어 있지 않으면 매크로로 구현 됩니다.

이전 버전과 호환성에 대 한 **isascii** 경우에만 매크로로 구현 됩니다 [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) 이 정의 되지 않았거나; 0으로 정의 하지 않으면 정의 되지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> 또는 \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h> 또는 \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> 또는 \<wchar.h>|

**isascii**, **__isascii** 및 **iswascii** 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
