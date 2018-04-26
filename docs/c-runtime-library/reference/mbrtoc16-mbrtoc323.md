---
title: mbrtoc16, mbrtoc323 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
dev_langs:
- C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 842950535dd71ba678e00a3203df17625ab50a4d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

반각 문자열의 첫 번째 멀티바이트 문자를 해당하는 UTF-16 또는 UTF-32 문자로 변환합니다.

## <a name="syntax"></a>구문

```C
size_t mbrtoc16(
   char16_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

size_t mbrtoc32(
   char32_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

```

### <a name="parameters"></a>매개 변수

*대상*<br/>
에 대 한 포인터는 **char16_t** 또는 **char32_t** 변환할 멀티 바이트 문자에 해당 합니다. Null인 경우 함수는 값을 저장하지 않습니다.

*소스*<br/>
변환할 멀티바이트 문자열의 포인터입니다.

*max_bytes*<br/>
최대 수의 바이트 *소스* 를 변환할 문자에 대 한 검사 합니다. 1과에 남아 있는 모든 null 종결자를 포함 한 바이트 수 사이의 값 이어야 합니다이 *소스*합니다.

*state*<br/>
에 대 한 포인터는 **mbstate_t** 변환 상태 개체를 하나 이상의 출력 문자로 멀티 바이트 문자열을 해석 하는 데 사용 합니다.

## <a name="return-value"></a>반환 값

성공할 경우 첫 번째 값을 반환 지정 된 현재 적용 되는 이러한 조건 중 *상태* 값:

|값|조건|
|-----------|---------------|
|0|다음 *max_bytes* 더 적은 문자에서 변환 또는 *소스* 경우 저장 된 값은 null 와이드 문자에 해당 *대상* null이 아닌 합니다.<br /><br /> *상태* 초기 이동 상태를 포함 합니다.|
|1 및 *max_bytes*(포함)|반환 값은의 바이트 수가 *소스* 유효한 멀티 바이트 문자를 완성 하는 합니다. 경우에 변환 된 와이드 문자는 저장 *대상* null입니다.|
|-3|에 저장 된 함수에 대 한 이전 호출에서 발생 하는 다음 와이드 문자가 *대상* 경우 *대상* null입니다. 바이트 *소스* 함수에이 호출에서 사용 됩니다.<br /><br /> 때 *소스* (예: 서로게이트 쌍)를 나타내려면 둘 이상의 와이드 문자가 멀티 바이트 문자를 가리키는 경우 *상태* 다음 함수 호출 작성 되도록 값이 업데이트  추가 문자입니다.|
|-2|다음 *max_bytes* 바이트는 완료 되지 않았지만 잠재적으로 유효한 멀티 바이트 문자를 나타냅니다. 값은 *대상*합니다. 이 결과 경우에 발생할 수 있습니다 *max_bytes* 은 0입니다.|
|-1|인코딩 오류가 발생했습니다. 다음 *max_bytes* 또는 이하의 바이트가 완전 하며 올바른 멀티 바이트 문자에 기여 하지 않습니다. 값은 *대상*합니다.<br /><br /> **EILSEQ** 에 저장 된 **errno** 및에서는 변환 상태가 *상태* 지정 되지 않았습니다.|

## <a name="remarks"></a>설명

**mbrtoc16** 까지 함수 읽습니다 *max_bytes* 바이트 *소스* 그 다음으로 첫 번째 완전 하 고 유효한 멀티 바이트 문자를 해당 하는 utf-16 저장소를 찾을 수 문자 *대상*합니다. 소스 바이트는 현재 스레드 멀티바이트 로캘에 따라 해석됩니다. 멀티 바이트 문자는 서로게이트 쌍을 같은 둘 이상의 utf-16 출력 문자를이 필요한 경우 그런 다음 *상태* 값에 다음 utf-16 문자를 저장 하도록 설정 된 *대상* 의다음호출**mbrtoc16**합니다. **mbrtoc32** 함수는 동일 하지만, 출력이 utf-32 문자로 저장 됩니다.

경우 *소스* 가 null 인 경우 반환 이러한 함수 호출의 해당 인수를 사용 하 여 **NULL** 에 대 한 *대상*, **""** 에대한*소스*에 1 *max_bytes*합니다. 전달 된 값의 *대상* 및 *max_bytes* 무시 됩니다.

경우 *소스* 은 null이 아닌 함수는 문자열의 시작 부분에서 시작 하 고 최대 검사 *max_bytes* 다음 멀티 바이트 문자를 완성 하는 데 필요한 바이트 수를 결정 하는 바이트 포함 이동 시퀀스입니다. 검사된 바이트에 유효하고 완전한 멀티바이트 문자가 포함되는 경우 함수는 문자를 해당하는 16비트 또는 32비트 와이드 문자로 변환합니다. 경우 *대상* null이 아닌 대상에 첫 번째 (및 유일 할 수 있음) 결과 문자 함수 저장 합니다. 에 값이 설정 추가 출력 문자가 필요한 경우 *상태*함수에 대 한 후속 호출에서 추가 문자를 출력 하 고-3 값 반환 되도록 합니다. 출력 문자가 더 이상 필요한 경우 다음 *상태* 초기 이동 상태로 설정 됩니다.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uchar.h>|\<cuchar>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
