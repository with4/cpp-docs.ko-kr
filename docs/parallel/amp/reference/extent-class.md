---
title: "extent 클래스 (c + + AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 28c90118eeb83df75f19b49f47ac884bff111b8f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="extent-class-c-amp"></a>extent 클래스(C++ AMP)
벡터를 나타냅니다 *N* 의 범위를 지정 하는 정수 값은 *N*-0 원점이 차원 공간입니다. 벡터의 값에서 가장 중요 한 최하위에 정렬 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
template <int _Rank>  
class extent;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 순위는 `extent` 개체입니다.  

 ## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[extent 생성자](#ctor)|`extent` 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[포함](#contains)|확인 하는 지정 된 `extent` 순위가 지정 된 개체입니다.|  
|[size](#size)|범위 (요소의 단위)에서 총 선형 크기를 반환합니다.|  
|[바둑판식으로 배열](#tile)|생성 된 `tiled_extent` 제공한 타일 익스텐트를 가진 개체 크기를 지정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator-](#operator_min)|새 반환 `extent` 를 빼는 방식으로 만들어진 개체에는 `index` 해당 요소 `extent` 요소입니다.|  
|[operator--](#operator_min_min)|감소의 각 요소는 `extent` 개체입니다.|  
|[operator%=](#operator_mod_eq)|모듈러스 (나머지)의 각 요소에 계산의 `extent` 해당 요소를 숫자로 나눌 때 개체입니다.|  
|[operator*=](#operator_star_eq)|각 요소를 곱한는 `extent` 개체 수입니다.|  
|[operator/=](#operator_min_eq)|분할의 각 요소는 `extent` 개체 수입니다.|  
|[extent:: operator\[\]](#operator_at)|지정된 된 인덱스에 있는 요소를 반환 합니다.|  
|[operator+](#operator_add)|새 반환 `extent` 해당 추가 하 여 만든 개체 `index` 및 `extent` 요소입니다.|  
|[operator++](#operator_add_add)|각 요소를 증가 `extent` 개체입니다.|  
|[operator+=](#operator_add_eq)|지정된 된 수의 각 요소에 추가 하는 `extent` 개체입니다.|  
|[operator=](#operator_eq)|다른 내용을 복사 `extent` 을 여기에 개체입니다.|  
|[operator-=](#operator_min_eq)|지정된 된 수의 각 요소에서 뺍니다는 `extent` 개체입니다.|  

  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[rank 상수](#rank)|차수를 가져옵니다는 `extent` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `extent`  


## <a name="contains"></a>포함 

나타냅니다 있는지 여부를 지정 된 [인덱스](index-class.md) 값 '범위' 개체에 포함 되어 있습니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool contains(const index<rank>& _Index) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 `index` 테스트할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`하는 경우 지정 된 `index` 에 포함 된 값의 `extent` 그렇지 그렇지 `false`합니다.  
  
##  <a name="ctor"></a>익스텐트 

'범위' 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent() restrict(amp,cpu);    
extent(const extent<_Rank>& _Other) restrict(amp,cpu);    
explicit extent(int _I) restrict(amp,cpu);    
extent(int _I0,  int _I1) restrict(amp,cpu);    
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);    
explicit extent(const int _Array[_Rank])restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Array`  
 배열을 `_Rank` 새를 만드는 데 사용 되는 정수 `extent` 개체입니다.  
  
 `_I`  
 범위의 길이입니다.  
  
 `_I0`  
 가장 중요 한 차원 길이 지정 합니다.  
  
 `_I1`  
 다음 기능을-가장 중요 한 차원 길이 지정 합니다.  
  
 `_I2`  
 덜 중요 한 차원 길이 지정 합니다.  
  
 `_Other`  
 `extent` 개체에서 새 `extent` 개체를 기반으로 합니다.  
  
## <a name="remarks"></a>설명  
 매개 변수가 없는 생성자는 `extent`&3; 순위를 가진 개체를 합니다.  
  
 배열 생성에 사용 되는 경우는 `extent` 개체 배열의 길이의 순위와 일치 해야는 `extent` 개체입니다.  
  
##  <a name="operator_mod_eq"></a>operator % = 

해당 요소를 숫자로 나눌 때의 모듈러스 (나머지)의 각 요소에 '범위'를 계산 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 모듈러스를 찾기 위한 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 `extent` 개체  
  
##  <a name="operator_star_eq"></a>연산자 * = 

지정 된 수 '범위' 개체의 각 요소를 곱합니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 곱할 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 `extent` 개체  
  
## <a name="operator_add"></a>operator + 

새 반환 `extent` 해당 추가 하 여 만든 개체 `index` 및 `extent` 요소입니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 `index` 를 추가 하려면 요소를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 새로운 `extent` 개체입니다.  
  
##  <a name="operator_add_add"></a>operator + + 

'범위' 개체의 각 요소를 증가 시킵니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator++() restrict(amp,cpu);    
extent<_Rank> operator++(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>반환 값  
 전위 연산자에 대 한는 `extent` 개체 (`*this`). 접미사 연산자에 대 한 새 `extent` 개체입니다.  
  
##  <a name="operator_add_eq"></a>+ = 연산자 

'범위' 개체의 각 요소에 지정된 된 숫자를 추가합니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 번호, 인덱스 또는 범위를 추가 하려면.  
  
### <a name="return-value"></a>반환 값  
 결과 `extent` 개체입니다.  
  
##  <a name="operator_min"></a>operator- 

새로 만듭니다 `extent` 개체에서 지정 된 각 요소를 빼서 `index` 이 해당 요소에서 개체 `extent` 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 `index` 뺄 요소를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 새로운 `extent` 개체입니다.  
  
##  <a name="operator_min_min"></a>-연산자 

감소 '범위' 개체의 각 요소입니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator--() restrict(amp,cpu);    
extent<_Rank> operator--(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>반환 값  
 전위 연산자에 대 한는 `extent` 개체 (`*this`). 접미사 연산자에 대 한 새 `extent` 개체입니다.  
  
##  <a name="operator_div_eq"></a>operator / = 

지정 된 수는 '범위' 개체의 각 요소를 나눕니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 나눌 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 `extent` 개체  
  
##  <a name="operator_min_eq"></a>-= 연산자 

'범위' 개체의 각 요소에서 지정된 된 숫자를 뺍니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 뺄 수입니다.  
  
### <a name="return-value"></a>반환 값  
 결과 `extent` 개체입니다.  
  
##  <a name="operator_eq"></a>연산자 = 

다른 '범위' 개체의 내용을 여기로 복사합니다.  
  
### <a name="syntax"></a>구문  
  
```  
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `extent` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `extent` 개체입니다.  
  
##  <a name="operator_at"></a>extent:: operator\[\] 
지정된 된 인덱스에 있는 요소를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
int operator[](unsigned int _Index) const restrict(amp,cpu);    
int& operator[](unsigned int _Index) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 0에서 1 뺀 값 순위 사이의 정수입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인덱스에 있는 요소입니다.  
  
##  <a name="rank_constant"></a>순위 

'범위' 개체의 차수를 저장 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="size"></a>크기 

`extent` 개체(요소의 단위에서)의 총 선형 크기 단위를 반환합니다.  
  
### <a name="syntax"></a>구문  

```  
unsigned int size() const restrict(amp,cpu);  
```  
  
## <a name="tile"></a>바둑판식으로 배열 

지정한 타일 크기를 tiled_extent 개체가 생성 됩니다.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```  
### <a name="parameters"></a>매개 변수
`_Dim0`바둑판식된 범위의의 가장 중요 한 구성 요소입니다.
`_Dim1`바둑판식된 범위의의 다음 기능을-가장 중요 한 구성 요소입니다.
`_Dim2`바둑판식된 범위의의 최하위 구성 요소입니다.


  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)

