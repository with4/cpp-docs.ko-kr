---
title: casin, casinf, casinl | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- casin
- casinf
- casinl
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
- casin
- casinf
- casinl
- complex/casin
- complex/casinf
- complex/casinl
dev_langs:
- C++
helpviewer_keywords:
- casin function
- casinf function
- casinl function
ms.assetid: b75d1455-7b1e-43b0-bd46-c530be190be9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c977430528d8fa5834d3959cbf0645bf68165f0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394579"
---
# <a name="casin-casinf-casinl"></a>casin, casinf, casinl

실제 축 따라 [-1, + 1] 간격 외부 분기 컷 복소수의 아크사인 값을 검색합니다.

## <a name="syntax"></a>구문

```C
_Dcomplex casin(
   _Dcomplex z
);
_Fcomplex casin(
   _Fcomplex z
);  // C++ only
_Lcomplex casin(
   _Lcomplex z
);  // C++ only
_Fcomplex casinf(
   _Fcomplex z
);
_Lcomplex casinl(
   _Lcomplex z
);
```

### <a name="parameters"></a>매개 변수

*z*<br/>
라디안으로 각도를 나타내는 복소수입니다.

## <a name="return-value"></a>반환 값

아크사인 값 *z*, 라디안에서입니다. 결과 허수 축을 따라 및 간격 내에 제한 [-π/2 + 2 π /] 실제 축을 따라 합니다.

## <a name="remarks"></a>설명

C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 **casin** 사용 하 고 반환 **_Fcomplex** 및 **_Lcomplex** 값입니다. C 프로그램에서 **casin** 항상 사용 하 고 반환 된 **_Dcomplex** 값입니다.

## <a name="requirements"></a>요구 사항

|루틴|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**casin**, **casinf**, **casinl**|\<complex.h>|\<ccomplex>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
