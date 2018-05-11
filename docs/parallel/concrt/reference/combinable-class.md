---
title: combinable 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
dev_langs:
- C++
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 695081e6513965a89222d1108c632e2f22580184
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="combinable-class"></a>combinable 클래스
`combinable<T>` 개체는 병렬 알고리즘 중에 잠금 없는 스레드 로컬 하위 계산을 수행하기 위해 데이터의 스레드 전용 복사본을 제공합니다. 병렬 작업이 끝나면 스레드 전용 하위 계산을 최종 결과에 병합할 수 있습니다. 이 클래스는 공유 변수 대신 사용될 수 있으며, 그렇지 않을 경우 해당 공유 변수에 대한 경합이 많으면 성능이 향상될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>
class combinable;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 병합 된 최종 결과의 데이터 형식입니다. 형식에는 복사 생성자 및 기본 생성자는 있어야 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[combinable](#ctor)|오버로드됨. 새 `combinable` 개체를 생성합니다.|  
|[~ combinable 소멸자](#dtor)|`combinable` 개체를 제거합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[clear](#clear)|이전 사용에서 중간 계산 결과 지웁니다.|  
|[combine](#combine)|제공된 된 combine 함수를 호출 하 여 스레드 로컬 하위 계산 집합의 최종 값을 계산 합니다.|  
|[combine_each](#combine_each)|스레드 로컬 하위 계산에 한 번씩 제공된 combine 함수를 호출 하 여 스레드 로컬 하위 계산 집합의 최종 값을 계산 합니다. 최종 결과 함수 개체에 의해 누적 됩니다.|  
|[local](#local)|오버로드됨. 스레드 전용 하위 계산에 대 한 참조를 반환합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator=](#operator_eq)|에 할당 한 `combinable` 개체에서 다른 `combinable` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `combinable`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="clear"></a> 지우기 

 이전 사용에서 중간 계산 결과 지웁니다.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> combinable 

 새 `combinable` 개체를 생성합니다.  
  
```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 초기화 함수 개체의 형식입니다.  
  
 `_FnInitialize`  
 형식의 각 새 스레드 전용 값을 초기화 호출 될 함수 `T`합니다. 서명 사용 하 여 함수 호출 연산자를 지원 해야 `T ()`합니다.  
  
 `_Copy`  
 기존 `combinable` 여기로 복사할 개체입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 형식에 대 한 기본 생성자를 사용 하 여 새 요소를 초기화 합니다. `T`합니다.  
  
 두 번째 생성자로 제공 된 초기화 함수를 사용 하 여 새 요소는 `_FnInitialize` 매개 변수입니다.  
  
 세 번째 생성자는 복사 생성자입니다.  
  
##  <a name="dtor"></a> ~ combinable 

 `combinable` 개체를 제거합니다.  
  
```
~combinable();
```  
  
##  <a name="combine"></a> 결합 

 제공된 된 combine 함수를 호출 하 여 스레드 로컬 하위 계산 집합의 최종 값을 계산 합니다.  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 두 스레드 로컬 하위 계산을 결합 하기 위해 호출 될 함수 개체의 형식입니다.  
  
 `_FnCombine`  
 하위 계산을 결합 하는 데 사용 되는 함수입니다. 해당 시그니처는 `T (T, T)` 또는 `T (const T&, const T&)`, 연관 및 누적 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 모든 스레드 전용 하위 계산을 결합 하 여 최종 결과입니다.  
  
##  <a name="combine_each"></a> combine_each 

 스레드 로컬 하위 계산에 한 번씩 제공된 combine 함수를 호출 하 여 스레드 로컬 하위 계산 집합의 최종 값을 계산 합니다. 최종 결과 함수 개체에 의해 누적 됩니다.  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Function`  
 단일 스레드 로컬 하위 계산을 결합 하기 위해 호출 될 함수 개체의 형식입니다.  
  
 `_FnCombine`  
 하나의 하위 계산을 결합 하는 데 사용 되는 함수입니다. 해당 시그니처는 `void (T)` 또는 `void (const T&)`, 연관 및 누적 이어야 합니다.  
  
##  <a name="local"></a> 로컬 

 스레드 전용 하위 계산에 대 한 참조를 반환합니다.  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Exists`  
 부울에 대 한 참조입니다. 이 인수에서 참조 하는 부울 값을로 설정 됩니다 `true` 하위 계산이 이미이 스레드에 존재 하 고로 설정 `false` 이것이이 스레드에 첫 번째 하위 계산 하는 경우.  
  
### <a name="return-value"></a>반환 값  
 스레드 전용 하위 계산에 대 한 참조입니다.  
  
##  <a name="operator_eq"></a> 연산자 = 

 에 할당 한 `combinable` 개체에서 다른 `combinable` 개체입니다.  
  
```
combinable& operator= (const combinable& _Copy);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Copy`  
 기존 `combinable` 여기로 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `combinable` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
