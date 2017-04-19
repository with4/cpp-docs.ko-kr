---
title: "&lt;thread&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7e849e8585b372b5b423a6c960aa926ac7d5cfec
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 하나의 `thread::id` 개체가 다른 개체보다 크거나 같은지를 확인합니다.  
  
```cpp  
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread::id` 개체입니다.  
  
 `Right`  
 오른쪽 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `!(Left < Right)`  
  
### <a name="remarks"></a>설명  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 하나의 `thread::id` 개체가 다른 개체보다 큰지를 확인합니다.  
  
```cpp  
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread::id` 개체입니다.  
  
 `Right`  
 오른쪽 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `Right < Left`  
  
### <a name="remarks"></a>설명  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 하나의 `thread::id` 개체가 다른 개체보다 작거나 같은지를 확인합니다.  
  
```cpp  
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread::id` 개체입니다.  
  
 `Right`  
 오른쪽 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `!(Right < Left)`  
  
### <a name="remarks"></a>설명  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 하나의 `thread::id` 개체가 다른 개체보다 작은지를 확인합니다.  
  
```cpp  
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread::id` 개체입니다.  
  
 `Right`  
 오른쪽 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 전체 순서에서 `Left`가 `Right` 앞에 오면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 연산자는 모든 `thread::id` 개체의 전체 순서를 정의합니다. 이러한 개체는 연관 컨테이너에서 키로 사용할 수 있습니다.  
  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="operator_neq"></a>  operator!=  
 두 `thread::id` 개체가 다른지 비교합니다.  
  
```cpp  
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread::id` 개체입니다.  
  
 `Right`  
 오른쪽 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `!(Left == Right)`  
  
### <a name="remarks"></a>설명  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="operator_eq_eq"></a>  operator==  
 두 `thread::id` 개체가 같은지 비교합니다.  
  
```cpp  
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread::id` 개체입니다.  
  
 `Right`  
 오른쪽 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개체가 실행의 동일 스레드를 나타내거나 어떤 개체도 실행의 스레드를 나타내지 않으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 `thread::id` 개체의 텍스트 표현을 스트림에 삽입합니다.  
  
```cpp  
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ostr`  
 [basic_ostream](../standard-library/basic-ostream-class.md) 개체입니다.  
  
 `Id`  
 `thread::id` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `Ostr`.  
  
### <a name="remarks"></a>설명  
 이 함수는 `Id`를 `Ostr`에 삽입합니다.  
  
 두 `thread::id` 개체가 비교 결과 같으면 해당 개체의 삽입된 텍스트 표현은 동일합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<thread>](../standard-library/thread.md)




