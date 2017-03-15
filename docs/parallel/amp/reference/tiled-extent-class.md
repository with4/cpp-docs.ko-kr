---
title: "tiled_extent 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tiled_extent
dev_langs:
- C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
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
ms.openlocfilehash: c2f7ebdb9c82ae24cf74064e710ddfb177670359
ms.lasthandoff: 02/24/2017

---
# <a name="tiledextent-class"></a>tiled_extent 클래스
A `tiled_extent` 개체는 `extent`&1;,&2; 또는&3; 차원 타일 익스텐트 공간 세분 하는&1; ~&3; 개의 차원 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
template <
    int _Dim0,  
    int _Dim1,  
    int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
 
template <
    int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dim0`  
 가장 중요 한 차원 길이 지정 합니다.  
  
 `_Dim1`  
 다음으로 가장 중요 한 차원 길이입니다.  
  
 `_Dim2`  
 덜 중요 한 차원 길이 지정 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[tiled_extent 생성자](#ctor)|`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.|  

  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[get_tile_extent 메서드](#tiled_extent__get_tile_extent)|반환 된 `extent` 개체의 값을 캡처하는 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|  
|[패드 메서드](#tiled_extent__pad)|새 반환 `tiled_extent` 익스텐트를 가진 개체는 타일 크기에 균등 하 게 나눌 수를 조정 합니다.|  
|[truncate 메서드](#tiled_extent__truncate)|새 반환 `tiled_extent` 타일 크기에 따라 균등 하 게 나눌 수를 낮게 조정 하는 익스텐트를 가진 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator = 연산자](#operator_eq)|지정 된 내용을 복사 `tiled_index` 을 여기에 개체입니다.|  

  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[tile_dim0 상수](#tiled_extent__tile_dim0)|가장 중요 한 차원 길이 저장합니다.|  
|[tile_dim1 상수](#tiled_extent__tile_dim1)|다음으로 가장 중요 한 차원 길이 저장합니다.|  
|[tile_dim2 상수](#tiled_extent__tile_dim2)|최하위 차원의 길이 저장합니다.|  

  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[tile_extent 데이터 멤버](#tiled_extent__tile_extent)|가져옵니다는 `extent` 개체의 값을 캡처하는 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  

## <a name="tiled_extent__ctor"></a> tiled_extent 생성자  
`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```  
tiled_extent();  
  
tiled_extent(  
    const Concurrency::extent<rank>& _Other );  
  
tiled_extent(  
    const tiled_extent& _Other );  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `extent` 또는 `tiled_extent` 복사할 개체입니다.  
  

  

## <a name="tiled_extent__get_tile_extent"></a> get_tile_extent   
반환 된 `extent` 개체의 값을 캡처하는 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.  
  
### <a name="syntax"></a>구문  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>반환 값  
 `extent` 개체의 크기를 캡처하는 `tiled_extent` 인스턴스.  
  

## <a name="tiled_extent__pad"></a>  pad   
새 반환 `tiled_extent` 익스텐트를 가진 개체는 타일 크기에 균등 하 게 나눌 수를 조정 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>반환 값  
 새 `tiled_extent` 값 개체입니다. 
## <a name="tiled_extent__truncate"></a> truncate   
새 반환 `tiled_extent` 타일 크기에 따라 균등 하 게 나눌 수를 낮게 조정 하는 익스텐트를 가진 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 새 반환 `tiled_extent` 타일 크기에 따라 균등 하 게 나눌 수를 낮게 조정 하는 익스텐트를 가진 개체입니다.  

## <a name="tiled_extent__operator_eq"></a> 연산자 =   
지정 된 내용을 복사 `tiled_index` 을 여기에 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `tiled_index` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `tiled_index` 인스턴스.  

## <a name="tiled_extent__tile_dim0"></a> tile_dim0   
가장 중요 한 차원 길이 저장합니다.  
  
### <a name="syntax"></a>구문  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tiled_extent__tile_dim1"></a> tile_dim1   
다음으로 가장 중요 한 차원 길이 저장합니다.  
  
### <a name="syntax"></a>구문  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_extent__tile_dim2"></a> tile_dim2   
최하위 차원의 길이 저장합니다.  
  
### <a name="syntax"></a>구문  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_extent__tile_extent"></a> tile_extent   
  가져옵니다는 `extent` 개체의 값을 캡처하는 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.  
  
### <a name="syntax"></a>구문  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

