---
title: "동시성 네임 스페이스 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 7fc7b500d882bb4e023904a147a7736996b5c5de
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators"></a>동시성 네임 스페이스 연산자
||||  
|-|-|-|  
|[연산자! = 연산자](#operator_neq)|[연산자&amp; &amp; 연산자](#operator_amp_amp)|[연산자&gt; 연산자](#operator_gt)|  
|[연산자&gt;= 연산자](#operator_gt_eq)|[연산자&lt; 연산자](#operator_lt)|[연산자&lt;= 연산자](#operator_lt_eq)|  
|[연산자 = = 연산자](#operator_eq_eq)|[operator|| Operator](#operator_lor)|  
  
##  <a name="a-nameoperatorlora--operator124124-operator"></a><a name="operator_lor"></a>연산자 | | 연산자  
 인수로 제공된 작업 중 하나가 성공적으로 완료될 경우 완료되는 작업을 만듭니다.  
  
```  
template<
    typename _ReturnType  
>  
task<_ReturnType>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>   operator||(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>매개 변수  
 `_ReturnType`  
 반환되는 작업의 형식입니다.  
  
 `_Lhs`  
 결과 작업으로 결합할 첫 번째 작업입니다.  
  
 `_Rhs`  
 결과 작업으로 결합할 두 번째 작업입니다.  
  
### <a name="return-value"></a>반환 값  
 두 입력 작업이 모두 성공적으로 완료된 경우 성공적으로 완료되는 작업입니다. 입력 작업이 `T` 형식이면 이 함수의 출력은 `task<std::vector<T>`가 됩니다. 입력 작업이 `void` 형식이면 이 함수의 출력 작업도 `task<void>`가 됩니다.  
  
### <a name="remarks"></a>주의  
 두 작업이 모두 취소되거나 예외를 throw하는 경우 반환된 작업은 취소된 상태로 완료되고, 예외가 발생한 경우 예외 중 하나가 해당 작업에 대해 `get()` 또는 `wait()`를 호출할 때 throw됩니다.  
  
##  <a name="a-nameoperatorampampa--operatorampamp-operator"></a><a name="operator_amp_amp"></a>연산자&amp; &amp; 연산자  
 인수로 제공된 두 작업이 모두 성공적으로 완료될 경우 완료되는 작업을 만듭니다.  
  
```  
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>    operator&&(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>매개 변수  
 `_ReturnType`  
 반환되는 작업의 형식입니다.  
  
 `_Lhs`  
 결과 작업으로 결합할 첫 번째 작업입니다.  
  
 `_Rhs`  
 결과 작업으로 결합할 두 번째 작업입니다.  
  
### <a name="return-value"></a>반환 값  
 두 입력 작업이 모두 성공적으로 완료되는 경우 완료되는 작업입니다. 입력 작업이 `T` 형식이면 이 함수의 출력은 `task<std::vector<T>>`가 됩니다. 입력 작업이 `void` 형식이면 이 함수의 출력 작업도 `task<void>`가 됩니다.  
  
### <a name="remarks"></a>주의  
 작업 중 하나를 취소하거나 예외를 throw하는 경우 반환된 작업을 취소된 상태에서 조기에 완료합니다. 그리고 해당 작업에서 `get()` 또는 `wait()`를 호출하는 경우 발견된 예외를 throw합니다.  
  
##  <a name="a-nameoperatoreqeqa--operator-operator"></a><a name="operator_eq_eq"></a>연산자 = = 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체와 같은지 테스트합니다.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 유형 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식을 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`연산자의 좌 변에 있는 동시 벡터가 연산자의 오른쪽에 있는 동시 벡터와 같은지 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 두 개의 동시 벡터는 동일한 수의 요소 및 해당 요소의 값이 서로 다르면 같습니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 이 메서드는 동시 벡터를 수정할 수 있는 다른 메서드에 대해 동시성이 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="a-nameoperatorneqa--operator-operator"></a><a name="operator_neq"></a>연산자! = 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체와 같지 않은지 테스트합니다.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 유형 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식을 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`동시 벡터 같지 않으면; `false` 동시 벡터 같으면 합니다.  
  
### <a name="remarks"></a>주의  
 두 개의 동시 벡터는 동일한 수의 요소 및 해당 요소의 값이 서로 다르면 같습니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 이 메서드는 동시 벡터를 수정할 수 있는 다른 메서드에 대해 동시성이 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="a-nameoperatorlta--operatorlt-operator"></a><a name="operator_lt"></a>연산자&lt; 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 작은지 테스트합니다.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 유형 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식을 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`연산자의 좌 변에 있는 동시 벡터가 연산자 우변에 있는 동시 벡터 보다 작은 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 연산자의 동작에 대 한 해당 하는 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시 벡터를 수정할 수 있는 다른 메서드에 대해 동시성이 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="a-nameoperatorlteqa--operatorlt-operator"></a><a name="operator_lt_eq"></a>연산자&lt;= 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 작거나 같은지 테스트합니다.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 유형 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식을 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`연산자의 좌 변에 있는 동시 벡터 보다 작거나 같음 연산자의 오른쪽에 있는 동시 벡터 작은 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 연산자의 동작에 대 한 해당 하는 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시 벡터를 수정할 수 있는 다른 메서드에 대해 동시성이 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="a-nameoperatorgta--operatorgt-operator"></a><a name="operator_gt"></a>연산자&gt; 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 큰지 테스트합니다.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 유형 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식을 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변에 있는 동시 벡터가 연산자 우변에 있는 동시 벡터보다 큰 경우 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 연산자의 동작에 대 한 해당 하는 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시 벡터를 수정할 수 있는 다른 메서드에 대해 동시성이 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="a-nameoperatorgteqa--operatorgt-operator"></a><a name="operator_gt_eq"></a>연산자&gt;= 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 크거나 같은지 테스트합니다.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 유형 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식을 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`연산자의 좌 변에 있는 동시 벡터 보다 크거나 같음 연산자의 오른쪽에 있는 동시 벡터 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 연산자의 동작에 대 한 해당 하는 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시 벡터를 수정할 수 있는 다른 메서드에 대해 동시성이 없습니다 `_A` 또는 `_B`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)

