---
title: isleadbyte, _isleadbyte_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
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
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 682cdde6983c5e590920c43418e510b9c275b34e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l

문자가 멀티바이트 문자의 선행 바이트인지 여부를 결정합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 정수입니다.

## <a name="return-value"></a>반환 값

**isleadbyte** 그렇지 않은 경우 인수가 0 또는 테스트 조건을 만족 하는 경우 0이 아닌 값을 반환 합니다. 문자 집합 (SBCS) 로캘 "C" 로캘 및 단일 바이트 **isleadbyte** 항상 0을 반환 합니다.

## <a name="remarks"></a>설명

**isleadbyte** 매크로 인수가 멀티 바이트 문자의 첫 번째 바이트인 경우 0이 아닌 값을 반환 합니다. **isleadbyte** -1에서 모든 정수 인수에 대 한 의미 있는 결과 생성 (**EOF**)를 **UCHAR_MAX** (0xFF) (포함).

예상된 인수 형식은 **isleadbyte** 은 **int**부호 있는 문자가 전달 되는 경우 컴파일러 수 변환 하는 정수 여 부호 확장을 예측할 수 없는 결과 생성 합니다.

이 함수의 버전은 **_l** 은 로캘 종속 동작에 현재 로캘 대신에 전달 된 로캘을 사용 하 여 접미사는 동일 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|항상 false를 반환합니다.|**_isleadbyte**|항상 false를 반환합니다.|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
