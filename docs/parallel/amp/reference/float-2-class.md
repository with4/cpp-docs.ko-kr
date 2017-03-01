---
title: "float_2 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_2::yx
- amp_short_vectors/Concurrency::graphics::float_2::operator-=
- amp_short_vectors/Concurrency::graphics::float_2::operator++
- amp_short_vectors/Concurrency::graphics::float_2::operator-
- amp_short_vectors/Concurrency::graphics::float_2::r
- amp_short_vectors/Concurrency::graphics::float_2::get_yx
- amp_short_vectors/Concurrency::graphics::float_2::get_xy
- amp_short_vectors/Concurrency::graphics::float_2::operator/=
- amp_short_vectors/Concurrency::graphics::float_2::set_yx
- amp_short_vectors/Concurrency::graphics::float_2::x
- amp_short_vectors/Concurrency::graphics::float_2::get_y
- amp_short_vectors/Concurrency::graphics::float_2::operator+=
- amp_short_vectors/Concurrency::graphics::float_2::gr
- amp_short_vectors/Concurrency::graphics::float_2::operator=
- amp_short_vectors/Concurrency::graphics::float_2::set_x
- amp_short_vectors/Concurrency::graphics::float_2::operator--
- amp_short_vectors/Concurrency::graphics::float_2::get_x
- amp_short_vectors/Concurrency::graphics::float_2::operator*=
- amp_short_vectors/Concurrency::graphics::float_2::rg
- amp_short_vectors/Concurrency::graphics::float_2::set_xy
- amp_short_vectors/Concurrency::graphics::float_2::xy
- amp_short_vectors/Concurrency::graphics::float_2
- amp_short_vectors/Concurrency::graphics::float_2::set_y
- amp_short_vectors/Concurrency::graphics::float_2::y
- amp_short_vectors/Concurrency::graphics::float_2::g
dev_langs:
- C++
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 05707bd43a8f9b89a93c0da0011c46d67361fc84
ms.lasthandoff: 02/24/2017

---
# <a name="float2-class"></a>float_2 클래스
두 부동 소수점의 short 벡터를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class float_2;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[float_2 생성자](#ctor)|오버로드됨. 기본 생성자를 0부터 모든 요소를 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|float_2::get_x 메서드||  
|float_2::get_xy 메서드||  
|float_2::get_y 메서드||  
|float_2::get_yx 메서드||  
|float_2::ref_g 메서드||  
|float_2::ref_r 메서드||  
|float_2::ref_x 메서드||  
|float_2::ref_y 메서드||  
|float_2::set_x 메서드||  
|float_2::set_xy 메서드||  
|float_2::set_y 메서드||  
|float_2::set_yx 메서드||  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|float_2::operator 연산자||  
|float_2::operator-연산자||  
|float_2::operator * = 연산자||  
|float_2::operator / = 연산자||  
|float_2::operator + + 연산자||  
|float_2::operator + = 연산자||  
|float_2::operator = 연산자||  
|float_2::operator-= 연산자||  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[상수 크기](#float_2__size)||  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|float_2::g 데이터 멤버||  
|float_2::gr 데이터 멤버||  
|float_2::r 데이터 멤버||  
|float_2::rg 데이터 멤버||  
|float_2::x 데이터 멤버||  
|float_2::xy 데이터 멤버||  
|float_2::y 데이터 멤버||  
|float_2::yx 데이터 멤버||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `float_2`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_short_vectors.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="a-namectora-float2"></a><a name="ctor"></a>float_2 

 기본 생성자를 0부터 모든 요소를 초기화 합니다.  
  
```  
float_2() restrict(amp,
    cpu);

 
float_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
float_2(
    float _V) restrict(amp,
    cpu);

 
float_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_V0`  
 0 요소를 초기화할 값입니다.  
  
 `_V1`  
 1 요소를 초기화할 값입니다.  
  
 `_V`  
 초기화에 대 한 값입니다.  
  
 `_Other`  
 초기화 하는 데 사용 되는 개체입니다.  
  
##  <a name="a-namefloat2sizea-size"></a><a name="float_2__size"></a>크기 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency:: graphics Namespace](concurrency-graphics-namespace.md)

