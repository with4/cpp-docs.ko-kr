---
title: texture_view 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- texture_view
- AMP_GRAPHICS/texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_alpha
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_blue
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_green
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_red
- AMP_GRAPHICS/Concurrency::graphics::texture_view::get
- AMP_GRAPHICS/Concurrency::graphics::texture_view::sample
- AMP_GRAPHICS/Concurrency::graphics::texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::texture_view::value_type
dev_langs:
- C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3db02d9cafb87c0f173546687ad01390e09b9f68
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696268"
---
# <a name="textureview-class"></a>texture_view 클래스
질감에 대 한 읽기 및 쓰기를 제공합니다. `texture_view` 값 형식이 변수인 텍스처를 읽을 수만 사용할 수 `int`, `unsigned int`, 또는 `float` 기본 32 비트 bpse 있는 합니다. 사용 하 여 다른 질감 형식을 읽으려면 `texture_view<const value_type, _Rank>`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename value_type,int _Rank>  
class texture_view;  
 
template<typename value_type, int _Rank>  
class texture_view 
   : public details::_Texture_base<value_type, _Rank>;  
 
template<typename value_type, int _Rank>  
class texture_view<const value_type, _Rank> 
   : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value_type`  
 질감 집계에 있는 요소의 형식입니다.  
  
 `_Rank`  
 순위는 `texture_view`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`value_type`|질감 집계에 있는 요소의 형식입니다.|  
|`coordinates_type`|텍셀은 다음을 지정 하는 데 사용 하는 좌표 유형의 `texture_view`-즉, 한 `short_vector` 의 값 형식이 지정 된 연결 된 질감으로 같은 순위를 가지는 `float`합니다.|  
|`gather_return_type`|반환 형식에 사용 되는 작업을 수집-즉, 순위 4 `short_vector` 보류 네 가지 형식이 같은 색상 구성 요소 샘플링 4 텍셀 값에서 수집 하 합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[texture_view 생성자](#ctor)|오버로드됨. 생성 된 `texture_view` 인스턴스.|  
|[~ texture_view 소멸자](#ctor)|소멸 된 `texture_view` 인스턴스.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[gather_alpha](#gather_alpha)|오버로드됨. 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 알파 (w) 구성 요소를 반환 합니다.|  
|[gather_blue](#gather_blue)|오버로드됨. 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 파랑 (z) 구성 요소를 반환 합니다.|  
|[gather_green](#gather_green)|오버로드됨. 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 녹색 (y) 구성 요소를 반환 합니다.|  
|[gather_red](#gather_red)|오버로드됨. 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 빨강 (x) 구성 요소를 반환 합니다.|  
|[get](#get)|오버로드됨. 인덱스 별로 요소 값을 가져옵니다.|  
|[sample](#sample)|오버로드됨. 지정 된 샘플링 구성을 사용 하 여 세부 수준 및 지정 된 좌표에서 질감을 샘플링 합니다.|  
|[set](#set)|인덱스에서 요소 값을 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator()](#operator_call)|오버로드됨. 인덱스 별로 요소 값을 가져옵니다.|  
|[operator[]](#operator_at)|오버로드됨. 인덱스 별로 요소 값을 가져옵니다.|  
|[operator=](#operator_eq)|오버로드됨. 대입 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[value_type](#value_type)|요소 값 형식의 `texture_view`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_Texture_base`  
  
 `texture_view`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_graphics.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="dtor"></a> ~ texture_view 

 소멸 된 `texture_view` 인스턴스.  
  
```  
~texture_view() restrict(amp, cpu);
```  
  
##  <a name="ctor"></a> texture_view 

 생성 된 `texture_view` 인스턴스.  
  
```  
texture_view(// [1] constructor  
    texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [2] constructor  
    texture<value_type, _Rank>& _Src,  
    unsigned int _Mipmap_level = 0) restrict(cpu);

 
texture_view(// [3] constructor  
    const texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [4] constructor  
    const texture<value_type, _Rank>& _Src,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);

 
texture_view(// [5] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [6] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [7] copy constructor  
    const texture_view<const value_type, _Rank>& _Other,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
 [1, 2] 생성자  
 `texture` 에 쓰기 가능한 `texture_view` 만들어집니다.  
  
 [3, 4] 생성자  
 `texture` 에 쓸 수 없는 `texture_view` 만들어집니다.  
  
 `_Other`  
 [5] 복사 생성자  
 쓰기 가능한 소스 `texture_view`합니다.  
  
 [6, 7] 복사 생성자  
 쓸 수 없는 소스 `texture_view`합니다.  
  
 `_Mipmap_level`  
 원본에 대해 특정 mip 맵 수준 `texture` 즉이 쓰기 가능한 `texture_view` 에 바인딩합니다. 기본값은 0 (가장 자세 함) 최상위 수준 mip 수준을 나타내는입니다.  
  
 `_Most_detailed_mip`  
 지정 하면 지정한 보기에 대 한 mip 수준 (가장 자세 함) 최상위 `texture_view` 개체입니다.  
  
 `_Mip_levels`  
 통해 액세스할 수 있는 mip 맵 수준의 수는 `texture_view`합니다.  
  
##  <a name="gather_red"></a> gather_red 

 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 빨강 (x) 구성 요소를 반환 합니다.  
  
```  
const gather_return_type gather_red(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_red(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Address_mode`  
 사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드를는 모든 차원에 대해 동일 합니다.  
  
 `_Sampler`  
 사용 하려면 샘플러 구성을 샘플에는 `texture_view`합니다.  
  
 `_Coord`  
 샘플 되려면 좌표입니다. 소수 자릿수 좌표 값은 샘플 텍셀 보간 하는 데 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 텍셀 값을 샘플링 하는 4의 빨강 (x) 구성 요소가 포함 된 4 차원 short 벡터.  
  
##  <a name="gather_green"></a> gather_green 

 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 녹색 (y) 구성 요소를 반환 합니다.  
  
```  
const gather_return_type gather_green(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_green(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Address_mode`  
 사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드를는 모든 차원에 대해 동일 합니다.  
  
 `_Sampler`  
 사용 하려면 샘플러 구성을 샘플에는 `texture_view`합니다.  
  
 `_Coord`  
 샘플 되려면 좌표입니다. 소수 자릿수 좌표 값은 샘플 텍셀 보간 하는 데 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 텍셀 값을 샘플링 하는 4의 녹색 (y) 구성 요소가 포함 된 4 차원 short 벡터.  
  
##  <a name="gather_blue"></a> gather_blue 

 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 파랑 (z) 구성 요소를 반환 합니다.  
  
```  
const gather_return_type gather_blue(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_blue(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Address_mode`  
 사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드를는 모든 차원에 대해 동일 합니다.  
  
 `_Sampler`  
 사용 하려면 샘플러 구성을 샘플에는 `texture_view`합니다.  
  
 `_Coord`  
 샘플 되려면 좌표입니다. 소수 자릿수 좌표 값은 샘플 텍셀 보간 하는 데 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 텍셀 값을 샘플링 하는 4의 빨강 (x) 구성 요소가 포함 된 4 차원 short 벡터.  
  
##  <a name="gather_alpha"></a> gather_alpha 

 지정 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 알파 (w) 구성 요소를 반환 합니다.  
  
```  
const gather_return_type gather_alpha(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_alpha(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Address_mode`  
 사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드를는 모든 차원에 대해 동일 합니다.  
  
 `_Sampler`  
 사용 하려면 샘플러 구성을 샘플에는 `texture_view`합니다.  
  
 `_Coord`  
 샘플 되려면 좌표입니다. 소수 자릿수 좌표 값은 샘플 텍셀 보간 하는 데 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 순위 4 짧은 벡터 알파 (w) 구성 요소는 4의 샘플링 텍셀 값을 포함 하 합니다.  
  
##  <a name="get"></a> 가져오기 

 지정된 된 인덱스에 요소 값을 가져옵니다.  
  
```  
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

 
value_type get(
    const index<_Rank>& _Index,  
    unsigned int _Mip_level = 0) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 다중 차원 수를 얻기 위해 요소의 인덱스입니다.  
  
 `_Mip_level`  
 값은 구했습니다 mip 맵 수준입니다. 기본값 0이 가장 자세한 mip 맵 수준을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 요소의 값입니다.  
  
##  <a name="operator_eq"></a> 연산자 = 

 지정 된 동일한 질감의 보기 할당 `texture_view` 이 `texture_view` 인스턴스.  
  
```  
texture_view<value_type, _Rank>& operator= (// [1] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view<const value_type, _Rank>& operator= (// [2] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

 
texture_view<const value_type, _Rank>& operator= (// [3] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 [1, 2] 복사 생성자  
 쓰기 가능한 `texture_view` 개체입니다.  
  
 [3] 복사 생성자  
 비-쓰기 가능한 `texture_view` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `texture_view` 인스턴스.  
  
##  <a name="operator_at"></a> operator] 

 인덱스에서 요소 값을 반환 합니다.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);

 
value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 인덱스, 다차원 것 같습니다.  
  
 `_I0`  
 1 차원 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 요소 값으로 인덱싱된 `_Index`합니다.  
  
##  <a name="operator_call"></a> operator) 

 인덱스에서 요소 값을 반환 합니다.  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,   int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);

 
value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
value_type operator() (
    int _I0) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 인덱스, 다차원 것 같습니다.  
  
 `_I0`  
 인덱스의 가장 중요 한 구성 요소입니다.  
  
 `_I1`  
 인덱스의 다음-에-가장 중요 한 구성 요소입니다.  
  
 `_I2`  
 인덱스의 최하위 구성 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 요소 값으로 인덱싱된 `_Index`합니다.  
  
##  <a name="sample"></a> 샘플 

 지정 된 샘플링 구성을 사용 하 여 세부 수준 및 지정 된 좌표에서 질감을 샘플링 합니다.  
  
```  
value_type sample(
    const sampler& _Sampler,  
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);

 
template<
    filter_mode _Filter_mode = filter_linear,  
    address_mode _Address_mode = address_clamp  
>  
value_type sample(
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Filter_mode`  
 texture_view 샘플링 하는 데 사용 되는 필터 모드입니다. 필터 모드가 최소화, 최대화, 및 mip 맵 필터에 대해 같습니다.  
  
 `_Address_mode`  
 texture_view 샘플링 하는 데 사용 되는 주소 모드입니다. 주소 모드를는 모든 차원에 대해 동일 합니다.  
  
 `_Sampler`  
 texture_view 샘플링 하는 데 샘플러 구성입니다.  
  
 `_Coord`  
 샘플 되려면 좌표입니다. 소수 자릿수 좌표 값 텍셀 값을 보간 하는 데 사용 됩니다.  
  
 `_Level_of_detail`  
 값에서 샘플링할 mip 맵 수준을 지정 합니다. 소수 값은 두 개의 mip 맵 수준 보간 하는 데 사용 됩니다. 기본 세부 정보 수준이 가장 자세한 mip 수준을 나타내는 0입니다.  
  
### <a name="return-value"></a>반환 값  
 보간된 샘플 값입니다.  
  
##  <a name="set"></a> 설정 

 지정된 된 값으로 지정된 된 인덱스에 요소 값을 설정합니다.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 다중 차원 수를 설정 하려면 요소의 인덱스입니다.  
  
 `value`  
 요소를 설정 값입니다.  
  
##  <a name="value_type"></a> value_type 

 값 형식에서 texture_view의 요소입니다.  
  
```  
typedef typename const value_type value_type;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
