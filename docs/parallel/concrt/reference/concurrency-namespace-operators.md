---
title: "동시성 네임 스페이스 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
dev_langs:
- C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad453a764a87d0d7e54b914b935fd46f56cd4cac
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-operators"></a>동시성 네임 스페이스 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|  
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|  
|[operator==](#operator_eq_eq)|[operator||](#operator_lor)|  
  
##  <a name="operator_lor"></a>  operator&#124;&#124; Operator  
 인수로 제공된 작업 중 하나가 성공적으로 완료될 경우 완료되는 작업을 만듭니다.  
  
```  
template<typename ReturnType>  
task<ReturnType> operator||(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void> operator||(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>매개 변수  
 `ReturnType`  
 반환되는 작업의 형식입니다.  
  
 `lhs`  
 결과 작업으로 결합할 첫 번째 작업입니다.  
  
 `rhs`  
 결과 작업으로 결합할 두 번째 작업입니다.  
  
### <a name="return-value"></a>반환 값  
 두 입력 작업이 모두 성공적으로 완료된 경우 성공적으로 완료되는 작업입니다. 입력 작업이 `T` 형식이면 이 함수의 출력은 `task<std::vector<T>`가 됩니다. 입력 작업이 `void` 형식이면 이 함수의 출력 작업도 `task<void>`가 됩니다.  
  
### <a name="remarks"></a>설명  
 두 작업이 모두 취소되거나 예외를 throw하는 경우 반환된 작업은 취소된 상태로 완료되고, 예외가 발생한 경우 예외 중 하나가 해당 작업에 대해 `get()` 또는 `wait()`를 호출할 때 throw됩니다.  
  
##  <a name="operator_amp_amp"></a>  연산자&amp; &amp; 연산자  
 인수로 제공된 두 작업이 모두 성공적으로 완료될 경우 완료되는 작업을 만듭니다.  
  
```  
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void>  operator&&(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>매개 변수  
 `ReturnType`  
 반환되는 작업의 형식입니다.  
  
 `lhs`  
 결과 작업으로 결합할 첫 번째 작업입니다.  
  
 `rhs`  
 결과 작업으로 결합할 두 번째 작업입니다.  
  
### <a name="return-value"></a>반환 값  
 두 입력 작업이 모두 성공적으로 완료되는 경우 완료되는 작업입니다. 입력 작업이 `T` 형식이면 이 함수의 출력은 `task<std::vector<T>>`가 됩니다. 입력 작업이 `void` 형식이면 이 함수의 출력 작업도 `task<void>`가 됩니다.  
  
### <a name="remarks"></a>설명  
 작업 중 하나를 취소하거나 예외를 throw하는 경우 반환된 작업을 취소된 상태에서 조기에 완료합니다. 그리고 해당 작업에서 `get()` 또는 `wait()`를 호출하는 경우 발견된 예외를 throw합니다.  
  
##  <a name="operator_eq_eq"></a>  operator== Operator  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체와 같은지 테스트합니다.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 연산자의 좌 변에 있는 동시 벡터가 연산자의 오른쪽에 있는 동시 벡터와 같은지 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 두 개의 동시 벡터는 동일한 수의 요소 및 해당 요소가 동일한 값이 있는 같습니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 이 메서드는 동시성 으로부터 안전한 동시 벡터를 수정할 수 있는 다른 메서드에 대해 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="operator_neq"></a>  operator! = 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체와 같지 않은지 테스트합니다.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 동시 벡터 같지 않으면 하는 경우 `false` 동시 벡터 같으면 합니다.  
  
### <a name="remarks"></a>설명  
 두 개의 동시 벡터는 동일한 수의 요소 및 해당 요소가 동일한 값이 있는 같습니다. 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 이 메서드는 동시성 으로부터 안전한 동시 벡터를 수정할 수 있는 다른 메서드에 대해 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="operator_lt"></a>  연산자&lt; 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 작은지 테스트합니다.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 연산자의 좌 변에 있는 동시 벡터가 연산자의 오른쪽에 있는 동시 벡터 보다 작은 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 동작에 대 한 해당 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시성 으로부터 안전한 동시 벡터를 수정할 수 있는 다른 메서드에 대해 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="operator_lt_eq"></a>  연산자&lt;= 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 작거나 같은지 테스트합니다.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 연산자의 좌 변에 있는 동시 벡터 보다 크거나 같음 연산자의 오른쪽에 있는 동시 벡터 작은 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 동작에 대 한 해당 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시성 으로부터 안전한 동시 벡터를 수정할 수 있는 다른 메서드에 대해 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="operator_gt"></a>  연산자&gt; 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 큰지 테스트합니다.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변에 있는 동시 벡터가 연산자 우변에 있는 동시 벡터보다 큰 경우 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 동작에 대 한 해당 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시성 으로부터 안전한 동시 벡터를 수정할 수 있는 다른 메서드에 대해 없습니다 `_A` 또는 `_B`합니다.  
  
##  <a name="operator_gt_eq"></a>  연산자&gt;= 연산자  
 연산자의 좌변에 있는 `concurrent_vector` 개체가 우변에 있는 `concurrent_vector` 개체보다 크거나 같은지 테스트합니다.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 동시 벡터에 저장 된 요소의 데이터 형식입니다.  
  
 `A1`  
 첫 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `A2`  
 두 번째 할당자 형식 `concurrent_vector` 개체입니다.  
  
 `_A`  
 `concurrent_vector` 형식의 개체입니다.  
  
 `_B`  
 `concurrent_vector` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 연산자의 좌 변에 있는 동시 벡터가 연산자의 오른쪽에 있는 동시 벡터 보다 크거나 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 동작에 대 한 해당 연산자와 같습니다는 `vector` 클래스에 `std` 네임 스페이스입니다.  
  
 이 메서드는 동시성 으로부터 안전한 동시 벡터를 수정할 수 있는 다른 메서드에 대해 없습니다 `_A` 또는 `_B`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
