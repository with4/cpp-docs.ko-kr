---
title: "Concurrency:: precise_math 네임 스페이스 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 73273a58f73860c77810a6ab59def560962f9539
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace-functions"></a>Concurrency:: precise_math 네임 스페이스 함수
||||  
|-|-|-|  
|[acos 함수](#acos)|[acosf 함수](#acosf)|[acosh 함수](#acosh)|  
|[acoshf 함수](#acoshf)|[asin 함수](#asin)|[asinf 함수](#asinf)|  
|[asinh 함수](#asinh)|[asinhf 함수](#asinhf)|[atan 함수](#atan)|  
|[atan2 함수](#atan2)|[atan2f 함수](#atan2f)|[atanf 함수](#atanf)|  
|[atanh 함수](#atanh)|[atanhf 함수](#atanhf)|[cbrt 함수](#cbrt)|  
|[cbrtf 함수](#cbrtf)|[ceil 함수](#ceil)|[ceilf 함수](#ceilf)|  
|[copysign 함수](#copysign)|[copysignf 함수](#copysignf)|[cos 함수](#cos)|  
|[cosf 함수](#cosf)|[cosh 함수](#cosh)|[coshf 함수](#coshf)|  
|[cospi 함수](#cospi)|[cospif 함수](#cospif)|[erf 함수](#erf)|  
|[erfc 함수](#erfc)|[erfcf 함수](#erfcf)|[erfcinv 함수](#erfcinv)|  
|[erfcinvf 함수](#erfcinvf)|[erff 함수](#erff)|[erfinv 함수](#erfinv)|  
|[erfinvf 함수](#erfinvf)|[exp 함수](#exp)|[exp10 함수](#exp10)|  
|[exp10f 함수](#exp10f)|[exp2 함수](#exp2)|[exp2f 함수](#exp2f)|  
|[expf 함수](#expf)|[expm1 함수](#expm1)|[expm1f 함수](#expm1f)|  
|[fabs 함수](#fabs)|[fabsf 함수](#fabsf)|[floor 함수](#floor)| 
|[fdim 함수](#fdim)|[fdimf 함수](#fdimf)|| 
|[floorf 함수](#floorf)|[fma 함수](#fma)|[fmaf 함수](#fmaf)|
[fmax 함수](#fmax)|[fmaxf 함수](#fmaxf)|| 
|[fmin 함수](#fmin)|[fminf 함수](#fminf)|[fmod 함수](#fmod)|  
|[fmodf 함수](#fmodf)|[fpclassify 함수](#fpclassify)|[frexp 함수](#frexp)|  
|[frexpf 함수](#frexpf)|[hypot 함수](#hypot)|[hypotf 함수](#hypotf)|  
|[ilogb 함수](#ilogb)|[ilogbf 함수](#ilogbf)|[isfinite 함수](#isfinite)|  
|[isinf 함수](#isinf)|[isnan 함수](#isnan)|[isnormal 함수](#isnormal)|  
|[ldexp 함수](#ldexp)|[ldexpf 함수](#ldexpf)|[lgamma 함수](#lgamma)|  
|[lgammaf 함수](#lgammaf)|[log 함수](#log)|[log10 함수](#log10)|  
|[log10f 함수](#log10f)|[log1p 함수](#log1p)|[log1pf 함수](#log1pf)|  
|[log2 함수](#log2)|[log2f 함수](#log2f)|[logb 함수](#logb)|  
|[logbf 함수](#logbf)|[logf 함수](#logf)|[modf 함수](#modf)|  
|[modff 함수](#modff)|[nan 함수](#nan)|[nanf 함수](#nanf)|  
|[nearbyint 함수](#nearbyint)|[nearbyintf 함수](#nearbyintf)|[nextafter 함수](#nextafter)|  
|[nextafterf 함수](#nextafterf)|[phi 함수](#phi)|[phif 함수](#phif)|  
|[pow 함수](#pow)|[powf 함수](#powf)|[probit 함수](#probit)|  
|[probitf 함수](#probitf)|[rcbrt 함수](#rcbrt)|[rcbrtf 함수](#rcbrtf)|  
|[remainder 함수](#remainder)|[remainderf 함수](#remainderf)|[remquo 함수](#remquo)|  
|[remquof 함수](#remquof)|[round 함수](#round)|[roundf 함수](#roundf)|  
|[rsqrt 함수](#rsqrt)|[rsqrtf 함수](#rsqrtf)|[scalb 함수](#scalb)|  
|[scalbf 함수](#scalbf)|[scalbn 함수](#scalbn)|[scalbnf 함수](#scalbnf)|  
|[signbit 함수](#signbit)|[signbitf 함수](#signbitf)|[sin 함수](#sin)|  
|[sincos 함수](#sincos)|[sincosf 함수](#sincosf)|[sinf 함수](#sinf)|  
|[sinh 함수](#sinh)|[sinhf 함수](#sinhf)|[sinpi 함수](#sinpi)|  
|[sinpif 함수](#sinpif)|[sqrt 함수](#sqrt)|[sqrtf 함수](#sqrtf)|  
|[tan 함수](#tan)|[tanf 함수](#tanf)|[tanh 함수](#tanh)|  
|[tanhf 함수](#tanhf)|[tanpi 함수](#tanpi)|[tanpif 함수](#tanpif)|  
|[tgamma 함수](#tgamma)|[tgammaf 함수](#tgammaf)|[trunc 함수](#trunc)|  
|[truncf 함수](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>acos 함수  
 인수의 아크코사인 값을 계산합니다.  
  
```  
inline float acos(float _X) restrict(amp);

 
inline double acos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 아크코사인 값을 반환합니다.  
  
##  <a name="a-nameacosfa--acosf-function"></a><a name="acosf"></a>acosf 함수  
 인수의 아크코사인 값을 계산합니다.  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 아크코사인 값을 반환합니다.  
  
##  <a name="a-nameacosha--acosh-function"></a><a name="acosh"></a>acosh 함수  
 인수의 역 하이퍼볼릭 코사인 값을 계산합니다.  
  
```  
inline float acosh(float _X) restrict(amp);

 
inline double acosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 하이퍼볼릭 코사인 값을 반환합니다.  
  
##  <a name="a-nameacoshfa--acoshf-function"></a><a name="acoshf"></a>acoshf 함수  
 인수의 역 하이퍼볼릭 코사인 값을 계산합니다.  
  
```  
inline float acoshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 하이퍼볼릭 코사인 값을 반환합니다.  
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>asin 함수  
 인수의 아크사인 값을 계산합니다.  
  
```  
inline float asin(float _X) restrict(amp);

 
inline double asin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 아크사인 값을 반환합니다.  
  
##  <a name="a-nameasinfa--asinf-function"></a><a name="asinf"></a>asinf 함수  
 인수의 아크사인 값을 계산합니다.  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 아크사인 값을 반환합니다.  
  
##  <a name="a-nameasinha--asinh-function"></a><a name="asinh"></a>asinh 함수  
 인수의 역 하이퍼볼릭 사인 값을 계산합니다.  
  
```  
inline float asinh(float _X) restrict(amp);

 
inline double asinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 하이퍼볼릭 사인 값을 반환합니다.  
  
##  <a name="a-nameasinhfa--asinhf-function"></a><a name="asinhf"></a>asinhf 함수  
 인수의 역 하이퍼볼릭 사인 값을 계산합니다.  
  
```  
inline float asinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 하이퍼볼릭 사인 값을 반환합니다.  
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>atan 함수  
 인수의 아크탄젠트를 계산합니다.  
  
```  
inline float atan(float _X) restrict(amp);

 
inline double atan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 아크탄젠트 값을 반환합니다.  
  
##  <a name="a-nameatan2a--atan2-function"></a><a name="atan2"></a>atan2 함수  
 _Y/_X의 아크탄젠트를 계산합니다.  
  
```  
inline float atan2(
    float _Y,  
    float _X) restrict(amp);

 
inline double atan2(
    double _Y,  
    double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Y`  
 부동 소수점 값  
  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _Y/_X의 아크탄젠트 값을 반환합니다.  
  
##  <a name="a-nameatan2fa--atan2f-function"></a><a name="atan2f"></a>atan2f 함수  
 _Y/_X의 아크탄젠트를 계산합니다.  
  
```  
inline float atan2f(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Y`  
 부동 소수점 값  
  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _Y/_X의 아크탄젠트 값을 반환합니다.  
  
##  <a name="a-nameatanfa--atanf-function"></a><a name="atanf"></a>atanf 함수  
 인수의 아크탄젠트를 계산합니다.  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 아크탄젠트 값을 반환합니다.  
  
##  <a name="a-nameatanha--atanh-function"></a><a name="atanh"></a>atanh 함수  
 인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.  
  
```  
inline float atanh(float _X) restrict(amp);

 
inline double atanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 하이퍼볼릭 탄젠트 값을 반환합니다.  
  
##  <a name="a-nameatanhfa--atanhf-function"></a><a name="atanhf"></a>atanhf 함수  
 인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.  
  
```  
inline float atanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 하이퍼볼릭 탄젠트 값을 반환합니다.  
  
##  <a name="a-namecbrta--cbrt-function"></a><a name="cbrt"></a>cbrt 함수  
 인수의 실제 세제곱근을 계산  
  
```  
inline float cbrt(float _X) restrict(amp);

 
inline double cbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 실제 세제곱근을 반환합니다.  
  
##  <a name="a-namecbrtfa--cbrtf-function"></a><a name="cbrtf"></a>cbrtf 함수  
 인수의 실제 세제곱근을 계산  
  
```  
inline float cbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 실제 세제곱근을 반환합니다.  
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil 함수  
 인수의 한계를 계산합니다.  
  
```  
inline float ceil(float _X) restrict(amp);

 
inline double ceil(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 한계를 반환합니다.  
  
##  <a name="a-nameceilfa--ceilf-function"></a><a name="ceilf"></a>ceilf 함수  
 인수의 한계를 계산합니다.  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 한계를 반환합니다.  
  
##  <a name="a-namecopysigna--copysign-function"></a><a name="copysign"></a>copysign 함수  
 _X 크기 및 _Y 부호 값을 생성합니다.  
  
```  
inline float copysign(
    float _X,  
    float _Y) restrict(amp);

 
inline double copysign(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X 크기 및 _Y 부호 값을 반환합니다.  
  
##  <a name="a-namecopysignfa--copysignf-function"></a><a name="copysignf"></a>copysignf 함수  
 _X 크기 및 _Y 부호 값을 생성합니다.  
  
```  
inline float copysignf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X 크기 및 _Y 부호 값을 반환합니다.  
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos 함수  
 인수의 코사인을 계산합니다.  
  
```  
inline float cos(float _X) restrict(amp);

 
inline double cos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 코사인 값을 반환합니다.  
  
##  <a name="a-namecosfa--cosf-function"></a><a name="cosf"></a>cosf 함수  
 인수의 코사인을 계산합니다.  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 코사인 값을 반환합니다.  
  
##  <a name="a-namecosha--cosh-function"></a><a name="cosh"></a>cosh 함수  
 인수의 하이퍼볼릭 코사인 값을 계산합니다.  
  
```  
inline float cosh(float _X) restrict(amp);

 
inline double cosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 코사인 값을 반환합니다.  
  
##  <a name="a-namecoshfa--coshf-function"></a><a name="coshf"></a>coshf 함수  
 인수의 하이퍼볼릭 코사인 값을 계산합니다.  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 코사인 값을 반환합니다.  
  
##  <a name="a-namecospia--cospi-function"></a><a name="cospi"></a>cospi 함수  
 pi * _X의 코사인 값을 계산합니다.  
  
```  
inline float cospi(float _X) restrict(amp);

 
inline double cospi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 pi * _X의 코사인 값을 반환합니다.  
  
##  <a name="a-namecospifa--cospif-function"></a><a name="cospif"></a>cospif 함수  
 pi * _X의 코사인 값을 계산합니다.  
  
```  
inline float cospif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 pi * _X의 코사인 값을 반환합니다.  
  
##  <a name="a-nameerfa--erf-function"></a><a name="erf"></a>erf 함수  
 _X의 오류 함수 계산  
  
```  
inline float erf(float _X) restrict(amp);

 
inline double erf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 오류 함수를 반환합니다.  
  
##  <a name="a-nameerfca--erfc-function"></a><a name="erfc"></a>erfc 함수  
 _X의 상보 오류 함수 계산  
  
```  
inline float erfc(float _X) restrict(amp);

 
inline double erfc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 상보 오류 함수를 반환합니다.  
  
##  <a name="a-nameerfcfa--erfcf-function"></a><a name="erfcf"></a>erfcf 함수  
 _X의 상보 오류 함수 계산  
  
```  
inline float erfcf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 상보 오류 함수를 반환합니다.  
  
##  <a name="a-nameerfcinva--erfcinv-function"></a><a name="erfcinv"></a>erfcinv 함수  
 _X의 역 상보 오류 함수 계산  
  
```  
inline float erfcinv(float _X) restrict(amp);

 
inline double erfcinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 역 상보 오류 함수를 반환합니다.  
  
##  <a name="a-nameerfcinvfa--erfcinvf-function"></a><a name="erfcinvf"></a>erfcinvf 함수  
 _X의 역 상보 오류 함수 계산  
  
```  
inline float erfcinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 역 상보 오류 함수를 반환합니다.  
  
##  <a name="a-nameerffa--erff-function"></a><a name="erff"></a>erff 함수  
 _X의 오류 함수 계산  
  
```  
inline float erff(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 오류 함수를 반환합니다.  
  
##  <a name="a-nameerfinva--erfinv-function"></a><a name="erfinv"></a>erfinv 함수  
 _X의 역 오류 함수 계산  
  
```  
inline float erfinv(float _X) restrict(amp);

 
inline double erfinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 역 오류 함수를 반환합니다.  
  
##  <a name="a-nameerfinvfa--erfinvf-function"></a><a name="erfinvf"></a>erfinvf 함수  
 _X의 역 오류 함수 계산  
  
```  
inline float erfinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 역 오류 함수를 반환합니다.  
  
##  <a name="a-nameexp10a--exp10-function"></a><a name="exp10"></a>exp10 함수  
 밑수&10; 인수의 지 수를 계산합니다.  
  
```  
inline float exp10(float _X) restrict(amp);

 
inline double exp10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 반환 된 밑이&10; 인 인수의 지 수  
  
##  <a name="a-nameexp10fa--exp10f-function"></a><a name="exp10f"></a>exp10f 함수  
 밑수&10; 인수의 지 수를 계산합니다.  
  
```  
inline float exp10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 반환 된 밑이&10; 인 인수의 지 수  
  
##  <a name="a-nameexpm1a--expm1-function"></a><a name="expm1"></a>expm1 함수  
 인수의 밑이 e인 지수 값 - 1을 계산합니다.  
  
```  
inline float expm1(float exponent) restrict(amp);

 
inline double expm1(double exponent) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `exponent`  
 지 수 항 *n* 수학식 `e` <sup>n</sup>여기서 `e` 는 자연 로그의 밑입니다.  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이 e인 지수 값 - 1을 반환합니다.  
  
##  <a name="a-nameexpm1fa--expm1f-function"></a><a name="expm1f"></a>expm1f 함수  
 인수의 밑이 e인 지수 값 - 1을 계산합니다.  
  
```  
inline float expm1f(float exponent) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `exponent`  
 지 수 항 *n* 수학식 `e` <sup>n</sup>여기서 `e` 는 자연 로그의 밑입니다.  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이 e인 지수 값 - 1을 반환합니다.  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>exp 함수  
 밑이 e 인 인수의 지 수를 계산합니다.  
  
```  
inline float exp(float _X) restrict(amp);

 
inline double exp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이 e인 지수 값을 반환합니다.  
  
##  <a name="a-nameexpfa--expf-function"></a><a name="expf"></a>expf 함수  
 밑이 e 인 인수의 지 수를 계산합니다.  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이 e인 지수 값을 반환합니다.  
  
##  <a name="a-nameexp2a--exp2-function"></a><a name="exp2"></a>exp2 함수  
 밑이&2; 인 인수의 지 수를 계산합니다.  
  
```  
inline float exp2(float _X) restrict(amp);

 
inline double exp2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&2;인 지수 값을 반환합니다.  
  
##  <a name="a-nameexp2fa--exp2f-function"></a><a name="exp2f"></a>exp2f 함수  
 밑이&2; 인 인수의 지 수를 계산합니다.  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&2;인 지수 값을 반환합니다.  
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>fabs 함수  
 인수의 절대값을 반환합니다.  
  
```  
inline float fabs(float _X) restrict(amp);

 
inline double fabs(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 절대값을 반환합니다.  
  
##  <a name="a-namefabsfa--fabsf-function"></a><a name="fabsf"></a>fabsf 함수  
 인수의 절대값을 반환합니다.  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 절대값을 반환합니다.  

## <a name="a-namefdima-fdim-function"></a><a name="fdim"></a>fdim 함수  
인수 사이의 양의 차이 계산 합니다.
```  
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
``` 
### <a name="parameters"></a>매개 변수
`_X`부동 소수점 값 `_Y` 부동 소수점 값


### <a name="return-value"></a>반환 값
_X 및 _Y _X가 _Y; 보다 큰 경우의 차이점 그렇지 않으면, +&0;입니다.
 
## <a name="a-namefdimfa-fdimf-function"></a><a name="fdimf"></a>fdimf 함수
인수 사이의 양의 차이 계산 합니다.
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```
### <a name="parameters"></a>매개 변수
`_X`부동 소수점 값 `_Y` 부동 소수점 값

### <a name="return-value"></a>반환 값
_X 및 _Y _X가 _Y; 보다 큰 경우의 차이점 그렇지 않으면, +&0;입니다. 
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>floor 함수  
 인수의 밑을 계산합니다.  
  
```  
inline float floor(float _X) restrict(amp);

 
inline double floor(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑을 반환합니다.  
  
##  <a name="a-namefloorfa--floorf-function"></a><a name="floorf"></a>floorf 함수  
 인수의 밑을 계산합니다.  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑을 반환합니다.  

## <a name="a-namefma-fma-function"></a><a name="fma">fma 함수  
첫 번째 및 두 번째 지정 된 인수를의 곱을 계산 결과 지정된 된 세 번째 인수를 추가 합니다. 전체 계산을 단일 작업으로 수행 됩니다.
```
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```
### <a name="parameters"></a>매개 변수
`_X`첫 번째 부동 소수점 인수입니다.
`_Y`부동 소수점 두 번째 인수입니다.
`_Z`부동 소수점 세 번째 인수입니다.

### <a name="return-value"></a>반환 값
식의 결과 (_X * _Y) + _Z 합니다. 전체 계산이; 단일 작업으로 수행 되는 즉, 하위 식을 무한 정밀도로 계산 하는 하 고 최종 결과 반올림 됩니다. 

## <a name="a-namefmafa-fmaf-function"></a><a name="fmaf"></a>fmaf 함수  
첫 번째 및 두 번째 지정 된 인수를의 곱을 계산 결과 지정된 된 세 번째 인수를 추가 합니다. 전체 계산을 단일 작업으로 수행 됩니다.
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```  
### <a name="parameters"></a>매개 변수
`_X`첫 번째 부동 소수점 인수입니다.
`_Y`부동 소수점 두 번째 인수입니다.
`_Z`부동 소수점 세 번째 인수입니다.

### <a name="return-value"></a>반환 값
식의 결과 (_X * _Y) + _Z 합니다. 전체 계산이; 단일 작업으로 수행 되는 즉, 하위 식을 무한 정밀도로 계산 하는 하 고 최종 결과 반올림 됩니다.
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>fmax 함수  
 인수의 최대 숫자 값 결정  
  
```  
inline float fmax(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmax(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최대 숫자 값을 반환 합니다.  
  
##  <a name="a-namefmaxfa--fmaxf-function"></a><a name="fmaxf"></a>fmaxf 함수  
 인수의 최대 숫자 값 결정  
  
```  
inline float fmaxf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최대 숫자 값을 반환 합니다.  
  
##  <a name="a-namefmina--fmin-function"></a><a name="fmin"></a>fmin 함수  
 인수의 최소 숫자 값 결정  
  
```  
inline float fmin(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmin(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최소 숫자 값을 반환 합니다.  
  
##  <a name="a-namefminfa--fminf-function"></a><a name="fminf"></a>fminf 함수  
 인수의 최소 숫자 값 결정  
  
```  
inline float fminf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최소 숫자 값을 반환 합니다.  
  
##  <a name="a-namefmoda--fmod-function-c-amp"></a><a name="fmod"></a>fmod 함수 (c + + AMP)  
 첫 번째 지정 된 인수는 두 번째 지정 된 인수를 나눈 나머지를 계산 합니다.  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmod(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 첫 번째 부동 소수점 인수입니다.  
  
 `_Y`  
 부동 소수점 두 번째 인수입니다.  
  
### <a name="return-value"></a>반환 값  
 나머지 부분에서는 `_X` 나눈 `_Y`;의 값, 즉 `_X`  -  `_Y` *n*여기서 *n* 전체 정수 되도록의 크기가 `_X`  -  `_Y` *n* 의 크기 보다 작으면 `_Y`합니다.  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>fmodf 함수  
 첫 번째 지정 된 인수는 두 번째 지정 된 인수를 나눈 나머지를 계산 합니다.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 첫 번째 부동 소수점 인수입니다.  
  
 `_Y`  
 부동 소수점 두 번째 인수입니다.  
  
### <a name="return-value"></a>반환 값  
 나머지 부분에서는 `_X` 나눈 `_Y`;의 값, 즉 `_X`  -  `_Y` *n*여기서 *n* 전체 정수 되도록의 크기가 `_X`  -  `_Y` *n* 의 크기 보다 작으면 `_Y`합니다.  
  
##  <a name="a-namefpclassifya--fpclassify-function"></a><a name="fpclassify"></a>fpclassify 함수  
 인수 값을 NaN, infinite, normal, subnormal,&0;으로 분류합니다.  
  
```  
inline int fpclassify(float _X) restrict(amp);

 
inline int fpclassify(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수 값에 적절한 번호 분류 매크로의 값을 반환합니다.  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>frexp 함수  
 가 수 및 _X의 지 수를 가져옵니다.  
  
```  
inline float frexp(
    float _X,  
    _Out_ int* _Exp) restrict(amp);

 
inline double frexp(
    double _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Exp`  
 부동 소수점 값의 _X의 정수 지수를 반환합니다.  
  
### <a name="return-value"></a>반환 값  
 _X의 가수를 반환합니다.  
  
##  <a name="a-namefrexpfa--frexpf-function"></a><a name="frexpf"></a>frexpf 함수  
 가 수 및 _X의 지 수를 가져옵니다.  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Exp`  
 부동 소수점 값의 _X의 정수 지수를 반환합니다.  
  
### <a name="return-value"></a>반환 값  
 _X의 가수를 반환합니다.  
  
##  <a name="a-namehypota--hypot-function"></a><a name="hypot"></a>hypot 함수  
 _X 및 _Y 제곱합의 제곱근 계산  
  
```  
inline float hypot(
    float _X,  
    float _Y) restrict(amp);

 
inline double hypot(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X 및 _Y 제곱합의 제곱근을 반환합니다.  
  
##  <a name="a-namehypotfa--hypotf-function"></a><a name="hypotf"></a>hypotf 함수  
 _X 및 _Y 제곱합의 제곱근 계산  
  
```  
inline float hypotf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X 및 _Y 제곱합의 제곱근을 반환합니다.  
  
##  <a name="a-nameilogba--ilogb-function"></a><a name="ilogb"></a>ilogb 함수  
 부호 있는 정수 값으로 _X 지수를 추출합니다.  
  
```  
inline int ilogb(float _X) restrict(amp);

 
inline int ilogb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 부호 있는 정수 값으로 _X 지수를 반환합니다.  
  
##  <a name="a-nameilogbfa--ilogbf-function"></a><a name="ilogbf"></a>ilogbf 함수  
 부호 있는 정수 값으로 _X 지수를 추출합니다.  
  
```  
inline int ilogbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 부호 있는 정수 값으로 _X 지수를 반환합니다.  
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>isfinite 함수  
 인수가 유한 인 값인에 있는지 여부를 결정 합니다.  
  
```  
inline int isfinite(float _X) restrict(amp);

 
inline int isfinite(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수가 유한인 값인 경우에만&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-nameisinfa--isinf-function"></a><a name="isinf"></a>isinf 함수  
 인수가 무한대 인지 결정 합니다.  
  
```  
inline int isinf(float _X) restrict(amp);

 
inline int isinf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수가 무한대 값인 경우에&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-nameisnana--isnan-function"></a><a name="isnan"></a>isnan 함수  
 인수가 NaN 인지 결정 합니다.  
  
```  
inline int isnan(float _X) restrict(amp);

 
inline int isnan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수가 NaN 값을 갖는 경우에만&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-nameisnormala--isnormal-function"></a><a name="isnormal"></a>isnormal 함수  
 인수가 정상인지 여부를 결정합니다.  
  
```  
inline int isnormal(float _X) restrict(amp);

 
inline int isnormal(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수가 정상 값을 가진 경우에만&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>ldexp 함수  
 지정 된가 수 및 지 수에서 숫자는 실수를 계산합니다.  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);

 
inline double ldexp(
    double _X,  
    double _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값가 수  
  
 `_Exp`  
 정수 값, 지 수  
  
### <a name="return-value"></a>반환 값  
 _X를 반환 합니다 * 2 ^ _Exp  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>ldexpf 함수  
 지정 된가 수 및 지 수에서 숫자는 실수를 계산합니다.  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값가 수  
  
 `_Exp`  
 정수 값, 지 수  
  
### <a name="return-value"></a>반환 값  
 _X를 반환 합니다 * 2 ^ _Exp  
  
##  <a name="a-namelgammaa--lgamma-function"></a><a name="lgamma"></a>lgamma 함수  
 감마 인수의 절대 값 자연 로그 계산  
  
```  
inline float lgamma(
    float _X,  
    _Out_ int* _Sign) restrict(amp);

 
inline double lgamma(
    double _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Sign`  
 부호를 반환합니다.  
  
### <a name="return-value"></a>반환 값  
 감마 인수의 절대 값의 자연 로그를 반환합니다.  
  
##  <a name="a-namelgammafa--lgammaf-function"></a><a name="lgammaf"></a>lgammaf 함수  
 감마 인수의 절대 값 자연 로그 계산  
  
```  
inline float lgammaf(
    float _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Sign`  
 부호를 반환합니다.  
  
### <a name="return-value"></a>반환 값  
 감마 인수의 절대 값의 자연 로그를 반환합니다.  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log 함수  
 인수의 밑이 e 인 로그 계산  
  
```  
inline float log(float _X) restrict(amp);

 
inline double log(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이 e인 로그 값을 반환합니다.  
  
##  <a name="a-namelog10a--log10-function"></a><a name="log10"></a>log10 함수  
 인수의 밑이&10; 인 로그 계산  
  
```  
inline float log10(float _X) restrict(amp);

 
inline double log10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&10;인 로그 값을 반환합니다.  
  
##  <a name="a-namelog10fa--log10f-function"></a><a name="log10f"></a>log10f 함수  
 인수의 밑이&10; 인 로그 계산  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&10;인 로그 값을 반환합니다.  
  
##  <a name="a-namelog1pa--log1p-function"></a><a name="log1p"></a>log1p 함수  
 인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.  
  
```  
inline float log1p(float _X) restrict(amp);

 
inline double log1p(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수에 1을 더한 값의 밑이 e인 로그 값을 반환합니다.  
  
##  <a name="a-namelog1pfa--log1pf-function"></a><a name="log1pf"></a>log1pf 함수  
 인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.  
  
```  
inline float log1pf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수에 1을 더한 값의 밑이 e인 로그 값을 반환합니다.  
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>log2 함수  
 인수의 밑이&2; 인 로그 계산  
  
```  
inline float log2(float _X) restrict(amp);

 
inline double log2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&10;인 로그 값을 반환합니다.  
  
##  <a name="a-namelog2fa--log2f-function"></a><a name="log2f"></a>log2f 함수  
 인수의 밑이&2; 인 로그 계산  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&10;인 로그 값을 반환합니다.  
  
##  <a name="a-namelogba--logb-function"></a><a name="logb"></a>logb 함수  
 부호 있는 정수 값으로서 _X의 지수를 부동 소수점 형식에서 추출합니다.  
  
```  
inline float logb(float _X) restrict(amp);

 
inline double logb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 부호 있는 지수를 반환합니다.  
  
##  <a name="a-namelogbfa--logbf-function"></a><a name="logbf"></a>logbf 함수  
 부호 있는 정수 값으로서 _X의 지수를 부동 소수점 형식에서 추출합니다.  
  
```  
inline float logbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 부호 있는 지수를 반환합니다.  
  
##  <a name="a-namelogfa--logf-function"></a><a name="logf"></a>logf 함수  
 인수의 밑이 e 인 로그 계산  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이 e인 로그 값을 반환합니다.  
  
##  <a name="a-namemodfa--modf-function"></a><a name="modf"></a>modf 함수  
 정수 부분과 소수 부분에 지정 된 인수를 분할합니다.  
  
```  
inline float modf(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);

 
inline double modf(
    double _X,  
    _Out_ double* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Iptr`(out 매개 변수)  
 정수 부분 `_X`, 부동 소수점 값으로.  
  
### <a name="return-value"></a>반환 값  
 부호 있는 소수 부분 `_X`합니다.  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>modff 함수  
 정수 부분과 소수 부분에 지정 된 인수를 분할합니다.  
  
```  
inline float modff(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Iptr`  
 정수 부분 `_X`, 부동 소수점 값으로.  
  
### <a name="return-value"></a>반환 값  
 부호 있는 소수 부분을 반환 `_X`합니다.  
  
##  <a name="a-namenana--nan-function"></a><a name="nan"></a>nan 함수  
 자동 NaN을 반환합니다.  
  
```  
inline double nan(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 사용 가능할 경우 _X에 표시된 내용과 함께 자동 NaN을 반환합니다.  
  
##  <a name="a-namenanfa--nanf-function"></a><a name="nanf"></a>nanf 함수  
 자동 NaN을 반환합니다.  
  
```  
inline float nanf(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 사용 가능할 경우 _X에 표시된 내용과 함께 자동 NaN을 반환합니다.  
  
##  <a name="a-namenearbyinta--nearbyint-function"></a><a name="nearbyint"></a>nearbyint 함수  
 인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림합니다.  
  
```  
inline float nearbyint(float _X) restrict(amp);

 
inline double nearbyint(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 반올림된 정수 값을 반환합니다.  
  
##  <a name="a-namenearbyintfa--nearbyintf-function"></a><a name="nearbyintf"></a>nearbyintf 함수  
 인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림합니다.  
  
```  
inline float nearbyintf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 반올림된 정수 값을 반환합니다.  
  
##  <a name="a-namenextaftera--nextafter-function"></a><a name="nextafter"></a>nextafter 함수  
 _Y 방향에서 _X 후 유형의 함수에서 다음 표현 가능 값 결정  
  
```  
inline float nextafter(
    float _X,  
    float _Y) restrict(amp);

 
inline double nextafter(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 함수 형식에 _y 방향에서 _X 후 다음으로 표현할 수 있는 값을 반환  
  
##  <a name="a-namenextafterfa--nextafterf-function"></a><a name="nextafterf"></a>nextafterf 함수  
 _Y 방향에서 _X 후 유형의 함수에서 다음 표현 가능 값 결정  
  
```  
inline float nextafterf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 함수 형식에 _y 방향에서 _X 후 다음으로 표현할 수 있는 값을 반환  
  
##  <a name="a-namephia--phi-function"></a><a name="phi"></a>phi 함수  
 인수는 누적 분포 함수를 반환합니다.  
  
```  
inline float phi(float _X) restrict(amp);

 
inline double phi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수는 누적 분포 함수를 반환합니다.  
  
##  <a name="a-namephifa--phif-function"></a><a name="phif"></a>phif 함수  
 인수는 누적 분포 함수를 반환합니다.  
  
```  
inline float phif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수는 누적 분포 함수를 반환합니다.  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>pow 함수  
 _X _y 거듭제곱을 계산 합니다.  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);

 
inline double pow(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값, 밑  
  
 `_Y`  
 부동 소수점 값, 지수  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-namepowfa--powf-function"></a><a name="powf"></a>powf 함수  
 _X _y 거듭제곱을 계산 합니다.  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값, 밑  
  
 `_Y`  
 부동 소수점 값, 지수  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-nameprobita--probit-function"></a><a name="probit"></a>probit 함수  
 인수의 역 누적 분포 함수를 반환합니다.  
  
```  
inline float probit(float _X) restrict(amp);

 
inline double probit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 누적 분포 함수를 반환합니다.  
  
##  <a name="a-nameprobitfa--probitf-function"></a><a name="probitf"></a>probitf 함수  
 인수의 역 누적 분포 함수를 반환합니다.  
  
```  
inline float probitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 역 누적 분포 함수를 반환합니다.  
  
##  <a name="a-namercbrta--rcbrt-function"></a><a name="rcbrt"></a>rcbrt 함수  
 인수의 제곱근의 역을 반환합니다.  
  
```  
inline float rcbrt(float _X) restrict(amp);

 
inline double rcbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 제곱근의 역을 반환합니다.  
  
##  <a name="a-namercbrtfa--rcbrtf-function"></a><a name="rcbrtf"></a>rcbrtf 함수  
 인수의 제곱근의 역을 반환합니다.  
  
```  
inline float rcbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 제곱근의 역을 반환합니다.  
  
##  <a name="a-nameremaindera--remainder-function"></a><a name="remainder"></a>remainder 함수  
 나머지 계산: _X REM _Y  
  
```  
inline float remainder(
    float _X,  
    float _Y) restrict(amp);

 
inline double remainder(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X REM _Y를 반환합니다.  
  
##  <a name="a-nameremainderfa--remainderf-function"></a><a name="remainderf"></a>remainderf 함수  
 나머지 계산: _X REM _Y  
  
```  
inline float remainderf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X REM _Y를 반환합니다.  
  
##  <a name="a-nameremquoa--remquo-function"></a><a name="remquo"></a>remquo 함수  
 첫 번째 지정 된 인수는 두 번째 지정 된 인수를 나눈 나머지를 계산 합니다. 또한 두 번째는 지정 된 인수의 유효 숫자를 나눈 하는 첫 번째 지정 된 인수의 유효 숫자의 몫을 계산 하 고 세 번째 인수에 지정 된 위치를 사용 하 여 몫을 반환 합니다.  
  
```  
inline float remquo(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);

 
inline double remquo(
    double _X,  
    double _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 첫 번째 부동 소수점 인수입니다.  
  
 `_Y`  
 부동 소수점 두 번째 인수입니다.  
  
 `_Quo`(out 매개 변수)  
 소수 자릿수 비트의 몫을 반환 하는 데 사용 되는 정수 주소 `_X` 의 소수 자릿수 비트 나눈 `_Y`합니다.  
  
### <a name="return-value"></a>반환 값  
 나머지를 반환 `_X` 나눈 `_Y`합니다.  
  
##  <a name="a-nameremquofa--remquof-function"></a><a name="remquof"></a>remquof 함수  
 첫 번째 지정 된 인수는 두 번째 지정 된 인수를 나눈 나머지를 계산 합니다. 또한 두 번째는 지정 된 인수의 유효 숫자를 나눈 하는 첫 번째 지정 된 인수의 유효 숫자의 몫을 계산 하 고 세 번째 인수에 지정 된 위치를 사용 하 여 몫을 반환 합니다.  
  
```  
inline float remquof(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 첫 번째 부동 소수점 인수입니다.  
  
 `_Y`  
 부동 소수점 두 번째 인수입니다.  
  
 `_Quo`(out 매개 변수)  
 소수 자릿수 비트의 몫을 반환 하는 데 사용 되는 정수 주소 `_X` 의 소수 자릿수 비트 나눈 `_Y`합니다.  
  
### <a name="return-value"></a>반환 값  
 나머지를 반환 `_X` 나눈 `_Y`합니다.  
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>round 함수  
 _X 가장 가까운 정수로 반올림 합니다.  
  
```  
inline float round(float _X) restrict(amp);

 
inline double round(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 가장 가까운 정수를 반환합니다.  
  
##  <a name="a-nameroundfa--roundf-function"></a><a name="roundf"></a>roundf 함수  
 _X 가장 가까운 정수로 반올림 합니다.  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 가장 가까운 정수를 반환합니다.  
  
##  <a name="a-namersqrta--rsqrt-function"></a><a name="rsqrt"></a>rsqrt 함수  
 역 인수의 제곱근을 반환합니다.  
  
```  
inline float rsqrt(float _X) restrict(amp);

 
inline double rsqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 역 인수의 제곱근을 반환합니다.  
  
##  <a name="a-namersqrtfa--rsqrtf-function"></a><a name="rsqrtf"></a>rsqrtf 함수  
 역 인수의 제곱근을 반환합니다.  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 역 인수의 제곱근을 반환합니다.  
  
##  <a name="a-namescalba--scalb-function"></a><a name="scalb"></a>scalb 함수  
 _X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.  
  
```  
inline float scalb(
    float _X,  
    float _Y) restrict(amp);

 
inline double scalb(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X * (FLT_RADIX ^ _Y)를 반환합니다.  
  
##  <a name="a-namescalbfa--scalbf-function"></a><a name="scalbf"></a>scalbf 함수  
 _X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.  
  
```  
inline float scalbf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X * (FLT_RADIX ^ _Y)를 반환합니다.  
  
##  <a name="a-namescalbna--scalbn-function"></a><a name="scalbn"></a>scalbn 함수  
 _X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.  
  
```  
inline float scalbn(
    float _X,  
    int _Y) restrict(amp);

 
inline double scalbn(
    double _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 _X * (FLT_RADIX ^ _Y)를 반환합니다.  
  
##  <a name="a-namescalbnfa--scalbnf-function"></a><a name="scalbnf"></a>scalbnf 함수  
 _X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.  
  
```  
inline float scalbnf(
    float _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 _X * (FLT_RADIX ^ _Y)를 반환합니다.  
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>signbit 함수  
 _X의 부호가 음수인지 결정합니다.  
  
```  
inline int signbit(float _X) restrict(amp);

 
inline int signbit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 부호가 음수인 경우에만&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-namesignbitfa--signbitf-function"></a><a name="signbitf"></a>signbitf 함수  
 _X의 부호가 음수인지 결정합니다.  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 부호가 음수인 경우에만&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-namesina--sin-function"></a><a name="sin"></a>sin 함수  
 인수의 사인 값을 계산합니다.  
  
```  
inline float sin(float _X) restrict(amp);

 
inline double sin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 사인 값을 반환합니다.  
  
##  <a name="a-namesinfa--sinf-function"></a><a name="sinf"></a>sinf 함수  
 인수의 사인 값을 계산합니다.  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 사인 값을 반환합니다.  
  
##  <a name="a-namesincosa--sincos-function"></a><a name="sincos"></a>sincos 함수  
 _X의 사인 및 코사인 값을 계산합니다.  
  
```  
inline void sincos(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);

 
inline void sincos(
    double _X,  
    _Out_ double* _S,  
    _Out_ double* _C) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_S`  
 _X의 사인 값을 반환합니다.  
  
 `_C`  
 _X의 코사인 값을 반환합니다.  
  
##  <a name="a-namesincosfa--sincosf-function"></a><a name="sincosf"></a>sincosf 함수  
 _X의 사인 및 코사인 값을 계산합니다.  
  
```  
inline void sincosf(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_S`  
 _X의 사인 값을 반환합니다.  
  
 `_C`  
 _X의 코사인 값을 반환합니다.  
  
##  <a name="a-namesinha--sinh-function"></a><a name="sinh"></a>sinh 함수  
 인수의 하이퍼볼릭 사인 값을 계산합니다.  
  
```  
inline float sinh(float _X) restrict(amp);

 
inline double sinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 사인 값을 반환합니다.  
  
##  <a name="a-namesinhfa--sinhf-function"></a><a name="sinhf"></a>sinhf 함수  
 인수의 하이퍼볼릭 사인 값을 계산합니다.  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 사인 값을 반환합니다.  
  
##  <a name="a-namesinpia--sinpi-function"></a><a name="sinpi"></a>sinpi 함수  
 pi * _X의 사인 값을 계산합니다.  
  
```  
inline float sinpi(float _X) restrict(amp);

 
inline double sinpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 pi * _X의 사인 값을 반환합니다.  
  
##  <a name="a-namesinpifa--sinpif-function"></a><a name="sinpif"></a>sinpif 함수  
 pi * _X의 사인 값을 계산합니다.  
  
```  
inline float sinpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 pi * _X의 사인 값을 반환합니다.  
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>sqrt 함수  
 인수의 제곱근을 계산합니다.  
  
```  
inline float sqrt(float _X) restrict(amp);

 
inline double sqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 제곱근을 반환합니다.  
  
##  <a name="a-namesqrtfa--sqrtf-function"></a><a name="sqrtf"></a>sqrtf 함수  
 인수의 제곱근을 계산합니다.  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 제곱근을 반환합니다.  
  
##  <a name="a-nametana--tan-function"></a><a name="tan"></a>tan 함수  
 인수의 탄젠트 값을 계산합니다.  
  
```  
inline float tan(float _X) restrict(amp);

 
inline double tan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 탄젠트 값을 반환합니다.  
  
##  <a name="a-nametanfa--tanf-function"></a><a name="tanf"></a>tanf 함수  
 인수의 탄젠트 값을 계산합니다.  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 탄젠트 값을 반환합니다.  
  
##  <a name="a-nametanha--tanh-function"></a><a name="tanh"></a>tanh 함수  
 인수의 하이퍼볼릭 탄젠트 값을 계산합니다.  
  
```  
inline float tanh(float _X) restrict(amp);

 
inline double tanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 탄젠트 값을 반환합니다.  
  
##  <a name="a-nametanhfa--tanhf-function"></a><a name="tanhf"></a>tanhf 함수  
 인수의 하이퍼볼릭 탄젠트 값을 계산합니다.  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 탄젠트 값을 반환합니다.  
  
##  <a name="a-nametanpia--tanpi-function"></a><a name="tanpi"></a>tanpi 함수  
 pi * _X의 탄젠트 값을 계산합니다.  
  
```  
inline float tanpi(float _X) restrict(amp);

 
inline double tanpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 pi * _X의 탄젠트 값을 반환합니다.  
  
##  <a name="a-nametanpifa--tanpif-function"></a><a name="tanpif"></a>tanpif 함수  
 pi * _X의 탄젠트 값을 계산합니다.  
  
```  
inline float tanpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 pi * _X의 탄젠트 값을 반환합니다.  
  
##  <a name="a-nametgammaa--tgamma-function"></a><a name="tgamma"></a>tgamma 함수  
 _X의 감마 함수 계산  
  
```  
inline float tgamma(float _X) restrict(amp);

 
inline double tgamma(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 감마 함수의 결과를 반환합니다.  
  
##  <a name="a-nametgammafa--tgammaf-function"></a><a name="tgammaf"></a>tgammaf 함수  
 _X의 감마 함수 계산  
  
```  
inline float tgammaf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X의 감마 함수의 결과를 반환합니다.  
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>trunc 함수  
 정수 구성 요소에 대 한 인수를 자릅니다.  
  
```  
inline float trunc(float _X) restrict(amp);

 
inline double trunc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 정수 구성 요소를 반환합니다.  
  
##  <a name="a-nametruncfa--truncf-function"></a><a name="truncf"></a>truncf 함수  
 정수 구성 요소에 대 한 인수를 자릅니다.  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 정수 구성 요소를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency:: precise_math Namespace](concurrency-precise-math-namespace.md)

