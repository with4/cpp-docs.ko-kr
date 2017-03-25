---
title: "index 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 52c19da3cb8de10c3963ca3b795cac1babb3dc7a
ms.lasthandoff: 03/17/2017

---
# <a name="index-class"></a>index 클래스
정의 *N*-차원 인덱스 pographics cpp amp.md 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Rank`  
 순위, 또는 차원의 수 있습니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[인덱스 생성자](#ctor)|`index` 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator--](#operator--)|감소의 각 요소는 `index` 개체입니다.|  
|[operator(mod) =](#operator_mod_eq)|모듈러스 (나머지)의 각 요소에 계산의 `index` 해당 요소를 숫자로 나눌 때 개체입니다.|  
|[operator*=](#operator_star_eq)|각 요소를 곱한는 `index` 개체 수입니다.|  
|[operator/=](#operator_div_eq)|분할의 각 요소는 `index` 개체 수입니다.|  
|[index:: operator\[\]](#operator_at)|지정된 된 인덱스에 있는 요소를 반환 합니다.|  
|[operator++](#operator_add_add)|각 요소를 증가 `index` 개체입니다.|  
|[operator+=](#operator_add_eq)|지정된 된 수의 각 요소에 추가 하는 `index` 개체입니다.|  
|[operator=](#operator_eq)|지정 된 내용을 복사 `index` 을 여기에 개체입니다.|  
|[operator-=](#operator_-_eq)|지정된 된 수의 각 요소에서 뺍니다는 `index` 개체입니다.|  

  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[rank 상수](#rank)|차수를 저장 된 `index` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `index`  
  
## <a name="remarks"></a>주의  
 `index` 구조 나타냅니다 좌표 벡터의 *N* 에서 고유한 위치를 지정 하는 정수는 *N*-차원 공간입니다. 벡터의 값에서 가장 중요 한 최하위에 정렬 됩니다. 구성 요소를 사용 하 여 값을 검색할 수 [연산자 =](#operator_eq)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  


## <a name="index_ctor"></a>인덱스 생성자
Index 클래스의 새 인스턴스를 초기화합니다.

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>매개 변수

_Array  
순위 값이 있는&1; 차원 배열입니다.  
(_I)  
1 차원 인덱스의 인덱스 위치입니다.  
_I0  
가장 중요 한 차원 길이 지정 합니다.  
_I1  
다음 기능을-가장 중요 한 차원 길이 지정 합니다.  
_I2  
덜 중요 한 차원 길이 지정 합니다.  
_Other  
새 인덱스 개체의 기반이 되는 인덱스 개체입니다.  

## <a name="operator--"></a>-연산자
감소 index 개체의 각 요소입니다.  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>반환 값
전위 연산자와 index 개체에 대 한 (*이). 접미사 연산자 인 새 인덱스 개체입니다.

## <a name="operator_mod_eq"></a>operator(mod) =   
해당 요소가 지정 된 숫자로 나눌 때의 모듈러스 (나머지) index 개체의 각 요소를 계산 합니다.

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>매개 변수
_Rhs를 모듈러스를 찾기 위해 나눌 숫자입니다.
Index 개체 값을 반환 합니다.

## <a name="operator_star_eq"></a>연산자 * =   
지정 된 수는 인덱스 개체의 각 요소를 곱합니다.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수
_Rhs는 곱할 숫자입니다.

## <a name="operator_div_eq"></a>operator / = 
지정된 된 숫자 인덱스 개체의 각 요소를 나눕니다.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>매개 변수
_Rhs를 나눌 수 있습니다.

## <a name="operator_at"></a>  operator\[\]  
지정 된 위치의 인덱스의 구성 요소를 반환 합니다.

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수
_Index 0에서 1 뺀 값 순위 사이의 정수입니다.

### <a name="return-value"></a>반환 값
지정된 된 인덱스에 있는 요소입니다.

### <a name="remarks"></a>설명
다음 예제에서는이 인덱스의 구성 요소 값을 표시합니다.
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>operator + +   
Index 개체의 각 요소를 증가 시킵니다.
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>반환 값
전위 연산자와 index 개체에 대 한 (*이). 접미사 연산자 인 새 인덱스 개체입니다.

## <a name="operator_add_eq"></a>+ = 연산자   
Index 개체의 각 요소에 지정된 된 숫자를 추가합니다.
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>매개 변수
_Rhs 추가할 수 있습니다.

### <a name="return-value"></a>반환 값
인덱스 개체입니다.

## <a name="operator_eq"></a>  operator=   
지정 된 인덱스 개체의 내용을 여기로 복사합니다.
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>매개 변수
_Other에서 복사할 인덱스 개체입니다.

### <a name="return-value"></a>반환 값
이 인덱스 개체에 대 한 참조입니다.

## <a name="operator_-_eq"></a>-= 연산자
Index 개체의 각 요소에서 지정된 된 숫자를 뺍니다.
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>매개 변수
_Rhs 뺄 수 있습니다.

### <a name="return-value"></a>반환 값
인덱스 개체입니다.   

## <a name="rank"></a>순위  
  Index 개체의 차수를 가져옵니다.
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)

