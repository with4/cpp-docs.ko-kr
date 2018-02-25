---
title: "uint_2 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_2::set_xy
- amp_short_vectors/Concurrency::graphics::uint_2::y
- amp_short_vectors/Concurrency::graphics::uint_2::gr
- amp_short_vectors/Concurrency::graphics::uint_2::operator-
- amp_short_vectors/Concurrency::graphics::uint_2::get_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator-=
- amp_short_vectors/Concurrency::graphics::uint_2::r
- amp_short_vectors/Concurrency::graphics::uint_2::yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator--
- amp_short_vectors/Concurrency::graphics::uint_2::set_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator=
- amp_short_vectors/Concurrency::graphics::uint_2::set_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator+=
- amp_short_vectors/Concurrency::graphics::uint_2::get_y
- amp_short_vectors/Concurrency::graphics::uint_2::xy
- amp_short_vectors/Concurrency::graphics::uint_2::x
- amp_short_vectors/Concurrency::graphics::uint_2::get_xy
- amp_short_vectors/Concurrency::graphics::uint_2::set_y
- amp_short_vectors/Concurrency::graphics::uint_2
- amp_short_vectors/Concurrency::graphics::uint_2::operator*=
- amp_short_vectors/Concurrency::graphics::uint_2::get_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator/=
- amp_short_vectors/Concurrency::graphics::uint_2::g
- amp_short_vectors/Concurrency::graphics::uint_2::operator++
- amp_short_vectors/Concurrency::graphics::uint_2::rg
dev_langs:
- C++
ms.assetid: 9fcc9129-72b1-4da7-9012-4d3be15f1c52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d7b3b494460e0f254f46ed197e09d6d8d485b5e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="uint2-class"></a>uint_2 클래스
두 개의 부호 없는 정수는 short 벡터를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class uint_2;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[uint_2 생성자](#ctor)|오버로드됨. 기본 생성자, 0 인 모든 요소를 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|uint_2::get_x||  
|uint_2::get_xy||  
|uint_2::get_y||  
|uint_2::get_yx||  
|uint_2::ref_g_Method||  
|uint_2::ref_r_Method||  
|uint_2::ref_x_Method||  
|uint_2::ref_y_Method||  
|uint_2::set_x||  
|uint_2::set_xy||  
|uint_2::set_y||  
|uint_2::set_yx||  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|uint_2::operator--||  
|uint_2::operator%=||  
|uint_2::operator&=||  
|uint_2::operator*=||  
|uint_2::operator/=||  
|uint_2::operator^=||  
|uint_2::operator&#124;=||  
|uint_2::operator~||  
|uint_2::operator++||  
|uint_2::operator+=||  
|uint_2::operator<\<=||  
|uint_2::operator=||  
|uint_2::operator-=||  
|uint_2::operator>>=||  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[size Constant](#uint_2__size)||  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|uint_2::g||  
|uint_2::gr||  
|uint_2::r||  
|uint_2::rg||  
|uint_2::x||  
|uint_2::xy||  
|uint_2::y||  
|uint_2::yx||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `uint_2`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_short_vectors.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="ctor"></a> uint_2 

 기본 생성자, 0 인 모든 요소를 초기화 합니다.  
  
```  
uint_2() restrict(amp,
    cpu);

 
uint_2(
    unsigned int _V0,  
    unsigned int _V1) restrict(amp,
    cpu);

 
uint_2(
    unsigned int _V) restrict(amp,
    cpu);

 
uint_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_V0`  
 값 초기화 요소 0입니다.  
  
 `_V1`  
 1 요소를 초기화 값입니다.  
  
 `_V`  
 초기화에 대 한 값입니다.  
  
 `_Other`  
 초기화 하는 데 사용 되는 개체입니다.  
  
##  <a name="uint_2__size"></a> 크기 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
