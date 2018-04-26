---
title: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
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
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
dev_langs:
- C++
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38463fdac8100edd89e2fead940ec82bd810f76b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="ismbslead-ismbstrail-ismbsleadl-ismbstraill"></a>_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l

멀티바이트 문자 문자열의 선행 바이트와 후행 바이트에 대한 상황에 맞는 테스트를 수행하고, 특정 부분 문자열 포인터가 선행 바이트를 가리키는지 아니면 후행 바이트를 가리키는지 여부를 결정합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _ismbslead(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbstrail(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbslead_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
int _ismbstrail_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
문자열의 시작이나 알려진 이전 선행 바이트를 가리키는 포인터입니다.

*current*<br/>
테스트할 문자열의 위치를 가리키는 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_ismbslead** 문자가 선행 바이트 이면-1을 반환 하 고 **_ismbstrail** 문자가 후행 바이트 이면-1을 반환 합니다. 입력 문자열이 유효하지만 선행 바이트나 후행 바이트가 아닌 경우 이러한 함수는 0을 반환합니다. 인수 중 하나가 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우 이러한 함수가 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

## <a name="remarks"></a>설명

**_ismbslead** 및 **_ismbstrail** 보다 속도가 느립니다는 **_ismbblead** 및 **_ismbbtrail** 버전 고려해 문자열 컨텍스트를 고려 하기 때문에 있습니다.

이 있는 이러한 함수 버전은 **_l** 은 로캘 종속 동작에은 현재 로캘 대신 전달 된 로캘을 사용 한다는 접미사는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbslead_l**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail_l**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* 테스트 조건에 대한 매니페스트 상수에 해당합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
