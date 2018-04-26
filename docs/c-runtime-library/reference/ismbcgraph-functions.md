---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ismbcpunct_l
- _ismbcblank
- _ismbcprint
- _ismbcgraph_l
- _ismbcblank_l
- _ismbcpunct
- _ismbcprint_l
- _ismbcspace_l
- _ismbcspace
- _ismbcgraph
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
- _ismbcspace
- _ismbcgraph
- _ismbcpunct
- ismbcspace_l
- ismbcgraph
- _ismbcgraph_l
- _ismbcprint
- _ismbcspace_l
- ismbcprint
- ismbcgraph_l
- ismbcspace
- ismbcpunct
dev_langs:
- C++
helpviewer_keywords:
- ismbcspace_l function
- _ismbcprint_l function
- ismbcspace function
- ismbcpunct function
- _ismbcspace_l function
- _ismbcprint function
- ismbcprint function
- _ismbcgraph function
- ismbcgraph_l function
- _ismbcpunct_l function
- ismbcpunct_l function
- ismbcprint_l function
- _ismbcpunct function
- ismbcgraph function
- _ismbcgraph_l function
- _ismbcspace function
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 332368dffa1cf75c15e58026ba089d75a8791940
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="ismbcgraph-ismbcgraphl-ismbcprint-ismbcprintl-ismbcpunct-ismbcpunctl-ismbcblank-ismbcblankl-ismbcspace-ismbcspacel"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l

문자가 그래픽 문자, 표시 문자, 문장 부호 문자 또는 공백 문자인지 여부를 확인합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _ismbcgraph(
   unsigned int c
);
int _ismbcgraph_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcprint(
   unsigned int c
);
int _ismbcprint_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcpunct(
   unsigned int c
);
int _ismbcpunct_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcblank(
   unsigned int c
);
int _ismbcblank_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcspace(
   unsigned int c
);
int _ismbcspace_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
확인할 문자입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

이러한 각 루틴은 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. 경우 *c* < 255 = 해당 하는 및 **_ismbb** 루틴 (예를 들어 **_ismbcalnum** 에 해당 **_ismbbalnum**), 결과 해당 반환 값 **_ismbb** 루틴입니다.

이러한 함수 버전은 제외 하는 것과 동일는 **_l** 접미사는 현재 로캘 대신은 로캘 종속 동작에 전달 된 로캘을 사용 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.

|루틴|테스트 조건|932 코드 페이지 예제|
|-------------|--------------------|---------------------------|
|**_ismbcgraph**|그래픽|0이 아닌 경우 및 경우에만 반환 *c* ASCII 또는 가타카나 인쇄 가능한 모든 문자는 공백 () 제외한의 단일 바이트 표현입니다.|
|**_ismbcprint**|인쇄 가능|0이 아닌 경우 및 경우에만 반환 *c* ASCII 또는 가타카나 인쇄 가능한 모든 문자는 공백 () 등의 단일 바이트 표현입니다.|
|**_ismbcpunct**|문장 부호|0이 아닌 경우 및 경우에만 반환 *c* 는 ASCII 또는 가타카나 문장 부호 문자의 싱글바이트 표현인 합니다.|
|**_ismbcblank**|공백 또는 가로 탭|0이 아닌 경우 및 경우에만 반환 *c* 공백 또는 가로 탭 문자는: *c*0x20 = 또는 *c*0x09 = 합니다.|
|**_ismbcspace**|공백|0이 아닌 경우 및 경우에만 반환 *c* 공백 문자: *c*= 0x20 또는 0x09 < =*c*< = 0x0D 합니다.|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_ismbcgraph**|\<mbstring.h>|
|**_ismbcgraph_l**|\<mbstring.h>|
|**_ismbcprint**|\<mbstring.h>|
|**_ismbcprint_l**|\<mbstring.h>|
|**_ismbcpunct**|\<mbstring.h>|
|**_ismbcpunct_l**|\<mbstring.h>|
|**_ismbcblank**|\<mbstring.h>|
|**_ismbcblank_l**|\<mbstring.h>|
|**_ismbcspace**|\<mbstring.h>|
|**_ismbcspace_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
