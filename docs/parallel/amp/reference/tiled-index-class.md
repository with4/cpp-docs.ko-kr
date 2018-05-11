---
title: tiled_index 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
dev_langs:
- C++
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd28ab01d0d4180cc518cff230eb7df8261f4940
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="tiledindex-class"></a>tiled_index 클래스
에 대 한 인덱스를 제공는 [tiled_extent](tiled-extent-class.md) 개체입니다. 이 클래스에 전역 원점을 기준으로 로컬 타일 원점을 기준으로 요소에 액세스 하는 속성이 있습니다. 바둑판식으로 배열 된 공간에 대 한 자세한 내용은 참조 [를 사용 하 여 타일](../../../parallel/amp/using-tiles.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <
    int _Dim0,  
    int _Dim1 = 0,  
    int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
 
template <
    int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Dim0`  
 가장 중요 한 차원 길이 지정 합니다.  
  
 `_Dim1`  
 다음 가장 중요 한 차원 길이 지정 합니다.  
  
 `_Dim2`  
 가장 덜 중요 한 차원 길이 지정 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[tiled_index 생성자](#ctor)|`tile_index` 클래스의 새 인스턴스를 초기화합니다.|  

  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[get_tile_extent](#tiled_index__get_tile_extent)|반환 된 [익스텐트](extent-class.md) 의 값을 가진 개체는 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|  


  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[barrier 상수](#tiled_index__barrier)|저장소는 [tile_barrier](tile-barrier-class.md) 스레드의 현재 타일 장벽을 나타내는 개체입니다.|  
|||  
|[전역 상수](#tiled_index__global)|저장소는 [인덱스](index-class.md) 에서 전역를 나타내는 차수 1, 2 또는 3 인덱스의 개체는 [그리드](http://msdn.microsoft.com/en-us/f7d1b6a6-586c-4345-b09a-bfc26c492cb0) 개체입니다.|  
|[지역 상수](#tiled_index__local)|저장소는 `index` 상대를 나타내는 차수 1, 2 또는 3 인덱스의 현재 타일에서의 개체는 [tiled_extent](tiled-extent-class.md) 개체입니다.|  
|[rank 상수](#tiled_index__rank)|차수를 저장 된 `tiled_index` 개체입니다.|  
|[tile 상수](#tiled_index__tile)|저장소는 `index` 차수 1, 2 또는 3의 현재 타일의 좌표를 나타내는의 개체는 `tiled_extent` 개체입니다.|  
|[tile_dim0 Constant](#tiled_index__tile_dim0)|가장 중요 한 차원 길이 저장합니다.|  
|[tile_dim1 상수](#tiled_index__tile_dim1)|다음 가장 중요 한 차원 길이 저장합니다.|  
|[tile_dim2 Constant](#tiled_index__tile_dim2)|가장 덜 중요 한 차원 길이 저장합니다.|  
|[tile_origin 상수](#tiled_index__tile_origin)|저장소는 `index` 개체의 현재 타일의 원점의 전역를 나타내는 차수 1, 2 또는 3 좌표는 `tiled_extent` 개체입니다.|  

  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|가져옵니다는 [익스텐트](extent-class.md) 의 값을 가진 개체는 `tiled_index` 템플릿 인수 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|  

  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  


## <a name="tiled_index__ctor"></a>  tiled_index 생성자  
`tiled_index` 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
tiled_index(  
    const index<rank>& _Global,  
    const index<rank>& _Local,  
    const index<rank>& _Tile,  
    const index<rank>& _Tile_origin,  
    const tile_barrier& _Barrier ) restrict(amp,cpu);  
  
tiled_index(  
    const tiled_index& _Other ) restrict(amp,cpu);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Global`  
 전역 [인덱스](index-class.md) 생성 된 `tiled_index`합니다.  
  
 `_Local`  
 로컬 [인덱스](index-class.md) 생성 된 `tiled_index`  
  
 `_Tile`  
 타일 [인덱스](index-class.md) 생성 된 `tiled_index`  
  
 `_Tile_origin`  
 타일 원점 [인덱스](index-class.md) 생성 된 `tiled_index`  
  
 `_Barrier`  
 [tile_barrier](tile-barrier-class.md) 생성 된 개체 `tiled_index`합니다.  
  
 `_Other`  
 `tile_index` 복사할 개체를 생성 된 `tiled_index`합니다.  
  
## <a name="overloads"></a>Overloads  
  
|||  
|-|-|  
|이름|설명|  
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|새 인스턴스를 초기화는 `tile_index` 전역 좌표에서 타일 및 타일 로컬 좌표에 내의 상대적인 위치의 인덱스에서 클래스입니다. `_Global` 및 `_Tile_origin` 매개 변수에서 계산 됩니다.|  
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|새 인스턴스를 초기화는 `tile_index` 지정 된 복사 하 여 클래스 `tiled_index` 개체입니다.|  


## <a name="tiled_index__get_tile_extent"></a>  get_tile_extent
반환 된 [익스텐트](extent-class.md) 의 값을 가진 개체는 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
extent<rank> get_tile_extent()restrict(amp,cpu);  
```  
  
## <a name="return-value"></a>반환 값  
 `extent` 템플릿 인수 `tiled_index`, `_Dim0` 및 `_Dim1`의 값을 가진 `_Dim2` 개체입니다.  

## <a name="tiled_index__barrier"></a>  barrier   
저장소는 [tile_barrier](tile-barrier-class.md) 스레드의 현재 타일 장벽을 나타내는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
const tile_barrier barrier;  
```  

## <a name="tiled_index__global"></a>  global   
저장소는 [인덱스](index-class.md) 개체는 개체의 전역 인덱스를 나타내는 차수 1, 2 또는 3입니다.  
  
## <a name="syntax"></a>구문  
  
```  
const index<rank> global;  
```  
  
## <a name="tiled_index__local"></a>  local   
저장소는 [인덱스](index-class.md) 상대를 나타내는 차수 1, 2 또는 3 인덱스의 현재 타일에서의 개체는 [tiled_extent](tiled-extent-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
const index<rank> local;  
```  
  
## <a name="tiled_index__rank"></a>  rank   
차수를 저장 된 `tiled_index` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
static const int rank = _Rank;  
```  

## <a name="tiled_index__tile"></a>  바둑판식으로 배열   
저장소는 [인덱스](index-class.md) 차수 1, 2 또는 3의 현재 타일의 좌표를 나타내는의 개체는 [tiled_extent](tiled-extent-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
const index<rank> tile;  
```  
  
## <a name="tiled_index__tile_dim0"></a>  tile_dim0  
가장 중요 한 차원 길이 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
static const int tile_dim0 = _Dim0;  
```  
   
## <a name="tiled_index__tile_dim1"></a>  tile_dim1   
다음 가장 중요 한 차원 길이 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_index__tile_dim2"></a>  tile_dim2   
가장 덜 중요 한 차원 길이 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_index__tile_origin"></a>  tile_origin   
저장소는 [인덱스](index-class.md) 개체 내에서 현재 타일의 원점의 전역를 나타내는 차수 1, 2 또는 3 좌표는 [tiled_extent](tiled-extent-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
const index<rank> tile_origin  
```  
## <a name="tile_extent"></a>  tile_extent
  가져옵니다는 [익스텐트](extent-class.md) 의 값을 가진 개체는 `tiled_index` 템플릿 인수 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
