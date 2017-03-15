---
title: "texture 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics::texture
dev_langs:
- C++
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 9
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
ms.openlocfilehash: aafb23ac4d366baed37f1cf667984253160af9c3
ms.lasthandoff: 02/24/2017

---
# <a name="texture-class"></a>texture 클래스
질감은 데이터에 집계는 `accelerator_view` 익스텐트 도메인에 있습니다. 익스텐트 도메인에 있는 각 요소에 대 한 변수 모음입니다. C + + 기본 형식에 해당 하는 값을 보유 하는 각 변수 ( `unsigned int`, `int`, `float`, `double`), 스칼라 형식 ( `norm`, 또는 `unorm`), 또는 short 벡터 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class texture;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value_type`  
 질감에 있는 요소의 형식입니다.  
  
 `_Rank`  
 질감의 순위입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`scalar_type`|스칼라 형식입니다.|  
|`value_type`|값 형식입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[질감 생성자](#ctor)|`texture` 클래스의 새 인스턴스를 초기화합니다.|  
|[~ texture 소멸자](#ctor)|소멸은 `texture` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[copy_to 메서드](#copy_to)|복사본은 `texture` 전체 복사본을 수행 하 여 대상 개체입니다.|  
|[데이터 메서드](#data)|이 질감의 원시 데이터에 대 한 CPU 포인터를 반환합니다.|  
|[get 메서드](#get)|지정된 된 인덱스에 있는 요소의 값을 반환합니다.|  
|[get_associated_accelerator_view 메서드](#get_associated_accelerator_view)|반환 된 [accelerator_view](accelerator-view-class.md) 에 복사 되도록이 질감에 대 한 기본 대상입니다.|  
|[get_depth_pitch 메서드](#get_depth_pitch)|각 깊이 조각 CPU에서 질감을 준비 하는 3d에서 사이의 바이트 수를 반환 합니다.|  
|[get_row_pitch 메서드](#get_row_pitch)|2D 또는 3D 텍스처 CPU에 준비의 각 행 사이의 바이트 수를 반환 합니다.|  
|[set 메서드](#set)|지정된 된 인덱스에 요소 값을 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator () 연산자](#operator_call)|매개 변수에 의해 지정 된 요소 값을 반환 합니다.|  
|[operator] 연산자](#operator_at)|지정된 된 인덱스에 있는 요소를 반환 합니다.|  
|[operator = 연산자](#operator_eq)|지정 된 복사 [질감](texture-class.md) 여기에 개체입니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[rank 상수](#rank)|차수를 가져옵니다는 `texture` 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[associated_accelerator_view 데이터 멤버](#associated_accelerator_view)|가져옵니다는 [accelerator_view](accelerator-view-class.md) 에 복사 되도록이 질감에 대 한 기본 대상입니다.|  
|[depth_pitch 데이터 멤버](#depth_pitch)|CPU에 준비 3D 텍스처의 각 깊이 조각 사이의 바이트 수를 가져옵니다.|  
|[row_pitch 데이터 멤버](#row_pitch)|2D 또는 3D의 각 행 사이의 바이트 수를 CPU에서 질감을 준비 가져옵니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_Texture_base`  
  
 `texture`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_graphics.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="a-namedtora-texture"></a><a name="dtor"></a>~ 질감 

 소멸은 `texture` 개체입니다.  
  
```  
~texture() restrict(cpu);
```  
  
##  <a name="a-nameassociatedacceleratorviewa-associatedacceleratorview"></a><a name="associated_accelerator_view"></a>associated_accelerator_view 

 가져옵니다는 [accelerator_view](accelerator-view-class.md) 에 복사 되도록이 질감에 대 한 기본 대상입니다.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namecopytoa-copyto"></a><a name="copy_to"></a>copy_to 

 복사본은 `texture` 전체 복사본을 수행 하 여 대상 개체입니다.  
  
```  
void copy_to(
    texture& _Dest) const;

 
 
void copy_to(
    writeonly_texture_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 복사할 개체입니다.  
  
 `_Rank`  
 질감의 순위입니다.  
  
 `value_type`  
 질감에 있는 요소의 형식입니다.  
  
##  <a name="a-namedataa-data"></a><a name="data"></a>데이터 

 이 질감의 원시 데이터에 대 한 CPU 포인터를 반환합니다.  
  
```  
void* data() restrict(cpu);

 
const void* data() const restrict(cpu);
```  
  
### <a name="return-value"></a>반환 값  
 질감의 원시 데이터에 대 한 포인터입니다.  
  
##  <a name="a-namedepthpitcha-depthpitch"></a><a name="depth_pitch"></a>depth_pitch 

 CPU에 준비 3D 텍스처의 각 깊이 조각 사이의 바이트 수를 가져옵니다.  
  
```  
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;  
```  
  
##  <a name="a-namegeta-get"></a><a name="get"></a>가져오기 

 지정된 된 인덱스에 있는 요소의 값을 반환합니다.  
  
```  
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 요소의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 인덱스에 있는 요소의 값입니다.  
  
##  <a name="a-namegetassociatedacceleratorviewa-getassociatedacceleratorview"></a><a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 복사할이 질감에 대 한 기본 설정 대상 accelerator_view를 반환 합니다.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```  
  
### <a name="return-value"></a>반환 값  
 [accelerator_view](accelerator-view-class.md) 에 복사 되도록이 질감에 대 한 기본 대상입니다.  
  
##  <a name="a-namegetdepthpitcha-getdepthpitch"></a><a name="get_depth_pitch"></a>get_depth_pitch 

 각 깊이 조각 CPU에서 질감을 준비 하는 3d에서 사이의 바이트 수를 반환 합니다.  
  
```  
unsigned int get_depth_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>반환 값  
 각 깊이 조각 CPU에서 질감을 준비 하는 3d에서 사이의 바이트 수입니다.  
  
##  <a name="a-namegetrowpitcha-getrowpitch"></a><a name="get_row_pitch"></a>get_row_pitch 

 2 차원 준비 텍스처의 각 행 사이 또는 각 행의 3 차원 준비 텍스처 깊이 조각 사이의 바이트 수를 반환합니다.  
  
```  
unsigned int get_row_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>반환 값  
 2 차원 준비 텍스처의 각 행 간이나 깊이 조각 3 차원 준비 텍스처의 각 행의 바이트 수입니다.  
  
##  <a name="a-nameoperatorcalla-operator"></a><a name="operator_call"></a>operator) 

 매개 변수에 의해 지정 된 요소 값을 반환 합니다.  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 인덱스입니다.  
  
 `_I0`  
 인덱스의 가장 중요 한 구성 요소입니다.  
  
 `_I1`  
 인덱스의 다음 기능을-가장 중요 한 구성 요소입니다.  
  
 `_I2`  
 인덱스의 최하위 구성 요소입니다.  
  
 `_Rank`  
 인덱스의 순위입니다.  
  
### <a name="return-value"></a>반환 값  
 매개 변수에 의해 지정 된 요소 값입니다.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>operator] 

 지정된 된 인덱스에 있는 요소를 반환 합니다.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 인덱스입니다.  
  
 `_I0`  
 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인덱스에 있는 요소입니다.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>연산자 = 

 지정 된 복사 [질감](texture-class.md) 여기에 개체입니다.  
  
```  
texture& operator= (
    const texture& _Other);

 
texture& operator= (
    texture<value_type, _Rank>&& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `texture` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `texture` 개체입니다.  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>순위 

 차수를 가져옵니다는 `texture` 개체입니다.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namerowpitcha-rowpitch"></a><a name="row_pitch"></a>row_pitch 

 2D 또는 3D의 각 행 사이의 바이트 수를 CPU에서 질감을 준비 가져옵니다.  
  
```  
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;  
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>설정 

 지정된 된 인덱스에 요소 값을 설정합니다.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 요소의 인덱스입니다.  
  
 `_Rank`  
 인덱스의 순위입니다.  
  
 `value`  
 요소의 새 값입니다.  
  
##  <a name="a-namectora-texture"></a><a name="ctor"></a>질감 

 `texture` 클래스의 새 인스턴스를 초기화합니다.  
  
```  
texture(
    const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

 
texture(
    int _E0) restrict(cpu);

 
texture(
    int _E0,  
    int _E1) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    const Concurrency::extent<_Rank>& _Ext, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1,  
    int _E2, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    const Concurrency::extent<_Rank>& _Ext, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1,  
    int _E2, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;  
 
texture(
    int _E0,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av)  ;  
 
texture(
    int _E0,  
    int _E1,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av)  ;  
 
texture(
    int _E0,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    const texture& _Src,  
    const Concurrency::accelerator_view& _Acc_view);

 
texture(
    texture&& _Other);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,   
    unsigned int _Bits_per_scalar_element,   
    const Concurrency::accelerator_view& _Av);

 
texture(
    const texture& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Acc_view`  
 [accelerator_view](accelerator-view-class.md) 질감의 위치를 지정 하는 합니다.  
  
 `_Av`  
 [accelerator_view](accelerator-view-class.md) 질감의 위치를 지정 하는 합니다.  
  
 `_Associated_av`  
 에 대 한 기본 대상 지정 하는 accelerator_view이이 텍스처에서 복사 합니다.  
  
 `_Bits_per_scalar_element`  
 질감의 스칼라 기본 형식에서 각 스칼라 요소당 비트 수입니다. 일반적으로 지원 되는 값은 8, 16, 32 및 64입니다. 0을 지정 된 비트 수가 기본 scalar_type 같습니다. 64 이중 기반 질감에만 유효합니다.  
  
 `_Ext`  
 질감의 각 차원에 대 한 범위입니다.  
  
 `_E0`  
 질감의 가장 중요 한 구성 요소입니다.  
  
 `_E1`  
 질감의 다음 기능을-가장 중요 한 구성 요소입니다.  
  
 `_E2`  
 질감의 범위의 최하위 구성 요소입니다.  
  
 `_Input_iterator`  
 입력된 interator의 형식입니다.  
  
 `_Mipmap_levels`  
 기본 질감에 mip 맵 수준의 수입니다. 0을 지정 하는 경우 텍스처 mip 맵 수준까지 지정 된 범위에 대 한 가능한 최소 크기의 전체 범위를 갖습니다.  
  
 `_Rank`  
 범위의 순위입니다.  
  
 `_Source`  
 호스트 버퍼에 대 한 포인터입니다.  
  
 `_Src`  
 복사 하는 질감입니다.  
  
 `_Src_byte_size`  
 소스 버퍼의 바이트 수입니다.  
  
 `_Src_first`  
 소스 컨테이너에는 시작 반복기입니다.  
  
 `_Src_last`  
 소스 컨테이너에 사용 되는 끝 반복기입니다.  
  
 `_Other`  
 다른 데이터 원본입니다.  
  
 `_Rank`  
 섹션의 순위입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency:: graphics Namespace](concurrency-graphics-namespace.md)

