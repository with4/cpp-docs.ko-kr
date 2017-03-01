---
title: "unorm_3 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-=
- amp_short_vectors/Concurrency::graphics::unorm_3::xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::rgb
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::br
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::b
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3
- amp_short_vectors/Concurrency::graphics::unorm_3::set_z
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::x
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::z
- amp_short_vectors/Concurrency::graphics::unorm_3::get_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator=
- amp_short_vectors/Concurrency::graphics::unorm_3::yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::gbr
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator--
- amp_short_vectors/Concurrency::graphics::unorm_3::operator/=
- amp_short_vectors/Concurrency::graphics::unorm_3::brg
- amp_short_vectors/Concurrency::graphics::unorm_3::gb
- amp_short_vectors/Concurrency::graphics::unorm_3::zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::rb
- amp_short_vectors/Concurrency::graphics::unorm_3::gr
- amp_short_vectors/Concurrency::graphics::unorm_3::zx
- amp_short_vectors/Concurrency::graphics::unorm_3::r
- amp_short_vectors/Concurrency::graphics::unorm_3::xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::grb
- amp_short_vectors/Concurrency::graphics::unorm_3::bg
- amp_short_vectors/Concurrency::graphics::unorm_3::get_y
- amp_short_vectors/Concurrency::graphics::unorm_3::g
- amp_short_vectors/Concurrency::graphics::unorm_3::yz
- amp_short_vectors/Concurrency::graphics::unorm_3::yx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_z
- amp_short_vectors/Concurrency::graphics::unorm_3::bgr
- amp_short_vectors/Concurrency::graphics::unorm_3::set_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-
- amp_short_vectors/Concurrency::graphics::unorm_3::y
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator++
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator+=
- amp_short_vectors/Concurrency::graphics::unorm_3::xz
- amp_short_vectors/Concurrency::graphics::unorm_3::rg
- amp_short_vectors/Concurrency::graphics::unorm_3::xy
- amp_short_vectors/Concurrency::graphics::unorm_3::operator*=
- amp_short_vectors/Concurrency::graphics::unorm_3::set_y
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::rbg
dev_langs:
- C++
ms.assetid: ea4e7a17-5256-464c-af28-8b01962564c0
caps.latest.revision: 10
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
ms.openlocfilehash: ce64e15c062f04df6c9f7671bd820ee188af0111
ms.lasthandoff: 02/24/2017

---
# <a name="unorm3-class"></a>unorm_3 클래스
3 가지 서명 되지 않은 일반 숫자의 short 벡터를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class unorm_3;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[unorm_3 생성자](#ctor)|오버로드됨. 기본 생성자를 0부터 모든 요소를 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|unorm_3::get_x 메서드||  
|unorm_3::get_xy 메서드||  
|unorm_3::get_xyz 메서드||  
|unorm_3::get_xz 메서드||  
|unorm_3::get_xzy 메서드||  
|unorm_3::get_y 메서드||  
|unorm_3::get_yx 메서드||  
|unorm_3::get_yxz 메서드||  
|unorm_3::get_yz 메서드||  
|unorm_3::get_yzx 메서드||  
|unorm_3::get_z 메서드||  
|unorm_3::get_zx 메서드||  
|unorm_3::get_zxy 메서드||  
|unorm_3::get_zy 메서드||  
|unorm_3::get_zyx 메서드||  
|Unorm_3::ref_b 메서드||  
|Unorm_3::ref_g 메서드||  
|Unorm_3::ref_r 메서드||  
|Unorm_3::ref_x 메서드||  
|Unorm_3::ref_y 메서드||  
|Unorm_3::ref_z 메서드||  
|unorm_3::set_x 메서드||  
|unorm_3::set_xy 메서드||  
|unorm_3::set_xyz 메서드||  
|unorm_3::set_xz 메서드||  
|unorm_3::set_xzy 메서드||  
|unorm_3::set_y 메서드||  
|unorm_3::set_yx 메서드||  
|unorm_3::set_yxz 메서드||  
|unorm_3::set_yz 메서드||  
|unorm_3::set_yzx 메서드||  
|unorm_3::set_z 메서드||  
|unorm_3::set_zx 메서드||  
|unorm_3::set_zxy 메서드||  
|unorm_3::set_zy 메서드||  
|unorm_3::set_zyx 메서드||  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|unorm_3::operator-연산자||  
|unorm_3::operator * = 연산자||  
|unorm_3::operator / = 연산자||  
|unorm_3::operator + + 연산자||  
|unorm_3::operator + = 연산자||  
|unorm_3::operator = 연산자||  
|unorm_3::operator-= 연산자||  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[상수 크기](#unorm_3__size)||  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|unorm_3::b 데이터 멤버||  
|unorm_3::bg 데이터 멤버||  
|unorm_3::bgr 데이터 멤버||  
|unorm_3::br 데이터 멤버||  
|unorm_3::brg 데이터 멤버||  
|unorm_3::g 데이터 멤버||  
|unorm_3::gb 데이터 멤버||  
|unorm_3::gbr 데이터 멤버||  
|unorm_3::gr 데이터 멤버||  
|unorm_3::grb 데이터 멤버||  
|unorm_3::r 데이터 멤버||  
|unorm_3::rb 데이터 멤버||  
|unorm_3::rbg 데이터 멤버||  
|unorm_3::rg 데이터 멤버||  
|unorm_3::rgb 데이터 멤버||  
|unorm_3::x 데이터 멤버||  
|unorm_3::xy 데이터 멤버||  
|unorm_3::xyz 데이터 멤버||  
|unorm_3::xz 데이터 멤버||  
|unorm_3::xzy 데이터 멤버||  
|unorm_3::y 데이터 멤버||  
|unorm_3::yx 데이터 멤버||  
|unorm_3::yxz 데이터 멤버||  
|unorm_3::yz 데이터 멤버||  
|unorm_3::yzx 데이터 멤버||  
|unorm_3::z 데이터 멤버||  
|unorm_3::zx 데이터 멤버||  
|unorm_3::zxy 데이터 멤버||  
|unorm_3::zy 데이터 멤버||  
|unorm_3::zyx 데이터 멤버||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `unorm_3`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_short_vectors.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="a-namectora-unorm3"></a><a name="ctor"></a>unorm_3 

 기본 생성자를 0부터 모든 요소를 초기화 합니다.  
  
```  
unorm_3() restrict(amp,
    cpu);

 
unorm_3(
    unorm _V0,  
    unorm _V1,  
    unorm _V2) restrict(amp,
    cpu);

 
unorm_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
unorm_3(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_3(
    float _V) restrict(amp,
    cpu);

 
unorm_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_V0`  
 0 요소를 초기화할 값입니다.  
  
 `_V1`  
 1 요소를 초기화할 값입니다.  
  
 `_V2`  
 2 요소를 초기화할 값입니다.  
  
 `_V`  
 초기화에 대 한 값입니다.  
  
 `_Other`  
 초기화 하는 데 사용 되는 개체입니다.  
  
##  <a name="a-nameunorm3sizea-size"></a><a name="unorm_3__size"></a>크기 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency:: graphics Namespace](concurrency-graphics-namespace.md)

