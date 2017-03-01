---
title: "Concurrency:: fast_math 네임 스페이스 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4a01f48a7d087281ab1e9222d1077e92ab8b0d6c
ms.openlocfilehash: 0545a57c492f5c1872c71c04c99b54f86b644102
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace-functions"></a>Concurrency:: fast_math 네임 스페이스 함수
||||  
|-|-|-|  
|[acos 함수](#acos)|[acosf 함수](#acosf)|[asin 함수](#asin)|  
|[asinf 함수](#asinf)|[atan 함수](#atan)|[atan2 함수](#atan2)|  
|[atan2f 함수](#atan2f)|[atanf 함수](#atanf)|[ceil 함수](#ceil)|  
|[ceilf 함수](#ceilf)|[cos 함수](#cos)|[cosf 함수](#cosf)|  
|[cosh 함수](#cosh)|[coshf 함수](#coshf)|[exp 함수](#exp)|  
|[exp2 함수](#exp2)|[exp2f 함수](#exp2f)|[expf 함수](#expf)|  
|[fabs 함수](#fabs)|[fabsf 함수](#fabsf)|[floor 함수](#floor)|  
|[floorf 함수](#floorf)|[fmax 함수](#fmax)|[fmaxf 함수](#fmaxf)|  
|[fmin 함수](#fmin)|[fminf 함수](#fminf)|[fmod 함수](#fmod)|  
|[fmodf 함수](#fmodf)|[frexp 함수](#frexp)|[frexpf 함수](#frexpf)|  
|[isfinite 함수](#isfinite)|[isinf 함수](#isinf)|[isnan 함수](#isnan)|  
|[ldexp 함수](#ldexp)|[ldexpf 함수](#ldexpf)|[log 함수](#log)|  
|[log10 함수](#log10)|[log10f 함수](#log10f)|[log2 함수](#log2)|  
|[log2f 함수](#log2f)|[logf 함수](#logf)|[modf 함수](#modf)|  
|[modff 함수](#modff)|[pow 함수](#pow)|[powf 함수](#powf)|  
|[round 함수](#round)|[roundf 함수](#roundf)|[rsqrt 함수](#rsqrt)|  
|[rsqrtf 함수](#rsqrtf)|[signbit 함수](#signbit)|[signbitf 함수](#signbitf)|  
|[sin 함수](#sin)|[sincos 함수](#sincos)|[sincosf 함수](#sincosf)|  
|[sinf 함수](#sinf)|[sinh 함수](#sinh)|[sinhf 함수](#sinhf)|  
|[sqrt 함수](#sqrt)|[sqrtf 함수](#sqrtf)|[tan 함수](#tan)|  
|[tanf 함수](#tanf)|[tanh 함수](#tanh)|[tanhf 함수](#tanhf)|  
|[trunc 함수](#trunc)|[truncf 함수](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>acos 함수  
 인수의 아크코사인 값을 계산합니다.  
  
```  
inline float acos(float _X) restrict(amp);
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
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>asin 함수  
 인수의 아크사인 값을 계산합니다.  
  
```  
inline float asin(float _X) restrict(amp);
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
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>atan 함수  
 인수의 아크탄젠트를 계산합니다.  
  
```  
inline float atan(float _X) restrict(amp);
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
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil 함수  
 인수의 한계를 계산합니다.  
  
```  
inline float ceil(float _X) restrict(amp);
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
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos 함수   
 인수의 코사인을 계산합니다.  
  
```  
inline float cos(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 하이퍼볼릭 코사인 값을 반환합니다.  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>exp 함수  
 밑이 e 인 인수의 지 수를 계산합니다.  
  
```  
inline float exp(float _X) restrict(amp);
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
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>fabs 함수  
 인수의 절대값을 반환합니다.  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
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
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>floor 함수  
 인수의 밑을 계산합니다.  
  
```  
inline float floor(float _X) restrict(amp);
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
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>fmax 함수  
 인수의 최대 숫자 값 결정  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
 `_Y`  
 정수 값  
  
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
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
 `_Y`  
 정수 값  
  
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
  
##  <a name="a-namefmoda--fmod-function"></a><a name="fmod"></a>fmod 함수  
 _X/_Y의 부동 소수점 나머지 계산  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X/_Y의 부동 소수점 나머지를 반환합니다.  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>fmodf 함수  
 _X/_Y의 부동 소수점 나머지를 계산합니다.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Y`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X/_Y의 부동 소수점 나머지를 반환합니다.  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>frexp 함수  
 가 수 및 _X의 지 수를 가져옵니다.  
  
```  
inline float frexp(
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
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>isfinite 함수  
 인수가 유한 인 값인에 있는지 여부를 결정 합니다.  
  
```  
inline int isfinite(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수가 NaN 값을 갖는 경우에만&0;이 아닌 값을 반환합니다.  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>ldexp 함수  
 가 수 및 지 수에서 숫자는 실수를 계산합니다.  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값, 가수  
  
 `_Exp`  
 정수 지수  
  
### <a name="return-value"></a>반환 값  
 _X를 반환 합니다 * 2 ^ _Exp  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>ldexpf 함수  
 가 수 및 지 수에서 숫자는 실수를 계산합니다.  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값, 가수  
  
 `_Exp`  
 정수 지수  
  
### <a name="return-value"></a>반환 값  
 _X를 반환 합니다 * 2 ^ _Exp  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log 함수  
 인수의 밑이 e 인 로그 계산  
  
```  
inline float log(float _X) restrict(amp);
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
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>log2 함수  
 인수의 밑이&2; 인 로그 계산  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 인수의 밑이&2; 인 로그 값을 반환  
  
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
 정수 부분과 소수 부분에 _X 분할합니다.  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Ip`  
  
### <a name="return-value"></a>반환 값  
 _X의 부호 있는 소수 부분을 반환합니다.  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>modff 함수  
 정수 부분과 소수 부분에 _X 분할합니다.  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
 `_Ip`  
  
### <a name="return-value"></a>반환 값  
 _X의 부호 있는 소수 부분을 반환합니다.  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>pow 함수  
 _X _y 거듭제곱을 계산 합니다.  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값, 밑  
  
 `_Y`  
 부동 소수점 값, 지수  
  
### <a name="return-value"></a>반환 값  
 _Y 거듭제곱을 _X의 값을 반환  
  
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
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>round 함수  
 _X 가장 가까운 정수로 반올림 합니다.  
  
```  
inline float round(float _X) restrict(amp);
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
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>signbit 함수  
 _X의 부호가 음수인지 결정합니다.  
  
```  
inline int signbit(float _X) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>sqrt 함수  
 인수의 제곱근을 계산합니다.  
  
```  
inline float sqrt(float _X) restrict(amp);
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
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>trunc 함수  
 정수 구성 요소에 대 한 인수를 자릅니다.  
  
```  
inline float trunc(float _X) restrict(amp);
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
 [Concurrency:: fast_math Namespace](concurrency-fast-math-namespace.md)

