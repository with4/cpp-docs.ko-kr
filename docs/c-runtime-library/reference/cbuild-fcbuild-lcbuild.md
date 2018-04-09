---
title: _Cbuild, _FCbuild, _LCbuild | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cbuild
- _FCbuild
- _LCbuild
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
dev_langs:
- C++
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d5a2a5f40266f490cc0d18614c63715192b0707
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2018
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

실수 및 허수 부분에서 복소수를 생성 합니다.

## <a name="syntax"></a>구문

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>매개 변수

*real*<br/>
생성 하려면 복소수의 실수 부분입니다.

*imaginary*<br/>
생성 하려면 복소수의 허수 부분입니다.

## <a name="return-value"></a>반환 값

A **_Dcomplex**, **_Fcomplex**, 또는 **_Lcomplex** 복소수를 나타내는 구조 (*실제*, *허수*  \* i) 지정 된 부동 소수점 형식의 값에 대 한 합니다.

## <a name="remarks"></a>설명

**_Cbuild**, **_FCbuild**, 및 **_LCbuild** 함수 복합 형식 만들기를 단순화 합니다. 사용 하 여는 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md) 및 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md) 표현 복소수의 실수 및 허수 부분을 검색 하는 함수입니다.

## <a name="requirements"></a>요구 사항

|루틴|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|`_Cbuild`,`_FCbuild`, `_LCbuild`|\<complex.h>|\<ccomplex>|

이러한 함수는 Microsoft 전용입니다. 형식을 **_Dcomplex**, **_Fcomplex**, 및 **_Lcomplex** 는 구현 되지 않은 C99 네이티브 형식에 해당 하는 Microsoft 전용 **double _Complex** , **_Complex float**, 및 **long double _Complex**각각. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](../../c-runtime-library/reference/cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](../../c-runtime-library/reference/cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)<br/>
[creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)<br/>
