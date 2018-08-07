---
title: 네임 스페이스 함수 Concurrency::graphics::direct3d | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
dev_langs:
- C++
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed95ed8df8a42dc62684c71a3005c2f33fecd18
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686336"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d 네임 스페이스 함수
||||  
|-|-|-|  
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|  
|[make_texture](#make_texture)|[msad4](#msad4)|  

 
##  <a name="get_sampler"></a>  get_sampler  
 Get 주어진된 accelerator는 D3D 샘플러 상태 인터페이스를 나타내는 지정된 샘플러 개체를 봅니다.  
  
```  
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,  
    const sampler& _Sampler) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Av`  
 만들 D3D 샘플러 상태는 D3D 액셀러레이터 보기입니다.  
  
 `_Sampler`  
 기본 D3D 샘플러 상태 인터페이스 만들어집니다는 샘플러 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 IUnknown 인터페이스 포인터에 해당 하는 D3D 샘플러 상태 지정된 샘플러를 나타내는입니다.  
  
##  <a name="get_texture"></a>  get_texture  
 지정 된 원본으로 사용 하는 Direct3D 텍스처 인터페이스를 가져옵니다 [질감](texture-class.md) 개체입니다.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

 
template<
    typename value_type,  
    int _Rank  
>  
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

 
template<
    typename value_type,  
    int _Rank  
>  
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);

 
```  
  
### <a name="parameters"></a>매개 변수  
 `value_type`  
 질감의 요소 형식입니다.  
  
 `_Rank`  
 질감의 순위입니다.  
  
 `_Texture`  
 질감 또는 Direct3D 텍스처 인터페이스에 있는 반환 accelerator_view와 관련 된 텍스처 보기.  
  
### <a name="return-value"></a>반환 값  
 에 해당 하는 질감 기본 Direct3D 텍스처 IUnknown 인터페이스 포인터입니다.  
  
##  <a name="make_sampler"></a>  make_sampler  
 D3D 샘플러 상태 인터페이스 포인터에서는 샘플러를 만듭니다.  
  
```  
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_D3D_sampler`  
 샘플러를 만들려는 D3D 샘플러 상태의 IUnknown 인터페이스 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 샘플러 제공된 D3D 샘플러 상태를 나타냅니다.  
  
##  <a name="make_texture"></a>  make_texture  
 만듭니다는 [질감](texture-class.md) 지정된 된 매개 변수를 사용 하 여 개체입니다.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,  
    _In_ IUnknown* _D3D_texture,  
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `value_type`  
 질감에 있는 요소의 형식입니다.  
  
 `_Rank`  
 질감의 순위입니다.  
  
 `_Av`  
 질감으로 하는 만들 수는 D3D 액셀러레이터 보기입니다.  
  
 `_D3D_texture`  
 D3D 질감에서 질감을 만드는 데의 IUnknown 인터페이스 포인터입니다.  
  
 `_View_format`  
 이 텍스처에서 만든 뷰의 경우 사용할 DXGI 형식입니다. _D3D_texture의 기본 형식 및이 템플릿의 value_type 형식을 파생할 DXGI_FORMAT_UNKNOWN (기본값)를 전달 합니다. 제공 된 서식 _D3D_texture의 기본 형식은 호환 되어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 제공 된 D3D 질감을 사용 하 여 질감입니다.  
  
##  <a name="msad4"></a>  msad4  
 4 바이트 참조 값과 8 바이트 소스 값을 비교 하 고 4 합계의 벡터를 누적 합니다. 각 합계는 마스크 된 제곱의 합 절대의 서로 다른 바이트 정렬 참조 값과 원본 값에 해당합니다.  
  
```  
inline uint4 msad4(
    uint _Reference,  
    uint2 _Source,  
    uint4 _Accum) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Reference`  
 하나의 uint 값에 4 바이트 배열을 참조  
  
 `_Source`  
 소스 배열 두 uint 값 형식의 한 벡터에 있는 8 바이트입니다.  
  
 `_Accum`  
 절대 차이점의 서로 다른 바이트 정렬 참조 값과 원본 값의 마스크 된 합계에 추가 될 4 개의 값의 벡터입니다.  
  
### <a name="return-value"></a>반환 값  
 4 합계의 벡터를 반환합니다. 각 합계는 마스크 된 제곱의 합 절대의 서로 다른 바이트 정렬 참조 값과 원본 값에 해당합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** amp_graphics.h  
  
 **Namespace:** Concurrency::graphics::direct3d 

## <a name="see-also"></a>참고 항목  
 [Concurrency::graphics::direct3d 네임스페이스](concurrency-graphics-direct3d-namespace.md)
