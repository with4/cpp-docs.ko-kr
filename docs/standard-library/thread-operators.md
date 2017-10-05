---
title: "&lt;thread&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
dev_langs:
- C++
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ff0fa361845c7bf64dd15bfc4e23be7b92b6cc39
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|  
|[operator==](#op_eq_eq)|  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
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
  
##  <a name="op_gt"></a>  operator&gt;  
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
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
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
  
##  <a name="op_lt"></a>  operator&lt;  
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
  
##  <a name="op_neq"></a>  operator!=  
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
  
##  <a name="op_eq_eq"></a>  operator==  
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
  
##  <a name="op_lt_lt"></a>  operator&lt;&lt;  
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




