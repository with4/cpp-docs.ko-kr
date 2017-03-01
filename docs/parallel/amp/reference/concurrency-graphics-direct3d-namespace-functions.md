---
title: "Concurrency::graphics::direct3d 네임 스페이스 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: aa7e91237eaa9ced297e2c5748359c23bb436df8
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d 네임 스페이스 함수
||||  
|-|-|-|  
|[get_sampler 함수](#get_sampler)|[get_texture 함수](#get_texture)|[make_sampler 함수](#make_sampler)|  
|[make_texture 함수](#make_texture)|[msad4 함수](#msad4)|  
  
##  <a name="a-namegetsamplera--getsampler-function"></a><a name="get_sampler"></a>get_sampler 함수  
 Get 주어진된 엑셀 러 레이 터는 D3D 샘플러 상태 인터페이스는이 나타내는 지정한 샘플러 개체를 봅니다.  
  
```  
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,  
    const sampler& _Sampler) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Av`  
 만들려는 D3D 샘플러 상태는 D3D 엑셀 러 레이 터 보기입니다.  
  
 `_Sampler`  
 기본 D3D 샘플러 상태 인터페이스 만들어집니다는 샘플러 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 주어진된 샘플러를 나타내는 D3D 샘플러 상태에 해당 하는 IUnknown 인터페이스 포인터입니다.  
  
##  <a name="a-namegettexturea--gettexture-function"></a><a name="get_texture"></a>get_texture 함수  
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
 질감 또는 Direct3D 텍스처 인터페이스에 있는 반환 되는 accelerator_view와 관련 된 텍스처 보기.  
  
### <a name="return-value"></a>반환 값  
 해당 내부 텍스처는 Direct3D 질감 하 IUnknown 인터페이스 포인터입니다.  
  
##  <a name="a-namemakesamplera--makesampler-function"></a><a name="make_sampler"></a>make_sampler 함수  
 D3D 샘플러 상태 인터페이스 포인터에서는 샘플러를 만듭니다.  
  
```  
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_D3D_sampler`  
 IUnknown 인터페이스 포인터에서 샘플러를 만든 D3D 샘플러 상태입니다.  
  
### <a name="return-value"></a>반환 값  
 샘플러 제공된 D3D 샘플러 상태를 나타냅니다.  
  
##  <a name="a-namemaketexturea--maketexture-function"></a><a name="make_texture"></a>make_texture 함수  
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
 만들려는 텍스처는 D3D 엑셀 러 레이 터 보기입니다.  
  
 `_D3D_texture`  
 D3D 질감에서 질감을 만드는의 IUnknown 인터페이스 포인터입니다.  
  
 `_View_format`  
 이 텍스처에서 만든 보기를 사용 하 여 DXGI 형식입니다. 파생 형식을 _D3D_texture의 기본 형식 및이 서식 파일의 value_type DXGI_FORMAT_UNKNOWN (기본값)를 전달 합니다. 제공 된 형식 _D3D_texture의 기본 형식은와 호환 되어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 제공 된 D3D 텍스처를 사용 하는 질감입니다.  
  
##  <a name="a-namemsad4a--msad4-function"></a><a name="msad4"></a>msad4 함수  
 4 바이트 참조 값과 8 바이트 소스 값을 비교 하 고 4 합계의 벡터를 누적 합니다. 각 합계는 마스킹된 제곱의 합 절대의 서로 다른 바이트 정렬 참조 값과 원본 값에 해당합니다.  
  
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
 소스 배열 두 uint 값의 벡터에서 8 바이트입니다.  
  
 `_Accum`  
 4 개의 절대 차이점의 서로 다른 바이트 정렬 참조 값과 원본 값의 마스크 된 합계에 추가할 값의 벡터입니다.  
  
### <a name="return-value"></a>반환 값  
 4 합계의 벡터를 반환합니다. 각 합계는 마스킹된 제곱의 합 절대의 서로 다른 바이트 정렬 참조 값과 원본 값에 해당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency::graphics::direct3d Namespace](concurrency-graphics-direct3d-namespace.md)

