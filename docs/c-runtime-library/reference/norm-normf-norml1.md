---
title: norm, normf, norml | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
dev_langs:
- C++
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e485c609054021fbdb8563ded539aa8f19cc868e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="norm-normf-norml"></a>norm, normf, norml

복소수의 제곱 크기를 검색합니다.

## <a name="syntax"></a>구문

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>매개 변수

*z*<br/>
복소수입니다.

## <a name="return-value"></a>반환 값

제곱된 크기가 *z*합니다.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **norm** 사용 하는 **_Fcomplex** 또는 **_Lcomplex** 값 및 반환 **float** 또는 **long double** 값입니다. C 프로그램에서 **norm** 항상 약간의 **_Dcomplex** 값과 반환은 **double** 값입니다.

## <a name="requirements"></a>요구 사항

|루틴|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**norm**, **normf**, **norml**|\<complex.h>|\<complex.h>|

**_Fcomplex**, **_Dcomplex**, 및 **_Lcomplex** 유형은 구현 되지 않은 네이티브 C99 형식의 해당 하는 Microsoft 전용 **_Complex float** , **double _Complex**, 및 **long double _Complex**각각.  호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
