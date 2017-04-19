---
title: "&lt;chrono&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
caps.latest.revision: 8
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c2ea4241ef1db4989caf8cdc6a16044d9c9381f6
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt; 연산자
||||  
|-|-|-|  
|[modulo 연산자](#operator_modulo)|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|  
|[operator&gt;=](#operator_gt__eq)|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator*](#operator_star)|[operator+](#operator_add)|[operator-](#operator-)|  
|[operator/](#operator_)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator-"></a>  operator-  
 [duration](../standard-library/duration-class.md) 및 [time_point](../standard-library/time-point-class.md) 개체의 빼기 또는 부정 연산자입니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type 
   operator-(
       const duration<Rep1, Period1>& Left, 
       cconst duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Rep2, class Period2>  
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type  
   operator-(
       const time_point<Clock, Duration1>& Time, 
       const duration<Rep2, Period2>& Dur);

 
template <class Clock, class Duration1, class Duration2>  
constexpr typename common_type<Duration1, Duration2>::type 
   operator-(
       const time_point<Clock, Duration1>& Left, 
       const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Time`  
 `time_point` 개체입니다.  
  
 `Dur`  
 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 함수는 간격 길이가 두 인수의 시간 간격 간 차이인 `duration` 개체를 반환합니다.  
  
 두 번째 함수는 `Time`으로 지정된 시점에서 `Dur`이 나타내는 시간 간격의 부정만큼 치환된 시점을 나타내는 `time_point` 개체를 반환합니다.  
  
 세 번째 함수는 `Left`와 `Right` 사이의 시간 간격을 나타내는 `duration` 개체를 반환합니다.  
  
##  <a name="operator_neq"></a>  operator!=  
 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체에 대한 같지 않음 연산자입니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);

 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 각 함수는 `!(Left == Right)`를 반환합니다.  
  
##  <a name="operator_star"></a>  operator*  
 [duration](../standard-library/chrono-operators.md#operator_star) 개체에 대한 곱하기 연산자입니다.  
  
```  
template <class Rep1, class Period1, class Rep2>  
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1> 
   operator*(
      const duration<Rep1, Period1>& Dur, 
      const Rep2& Mult);

 
template <class Rep1, class Rep2, class Period2>  
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2> 
   operator*(
       const Rep1& Mult,
       const duration<Rep2, 
       Period2>& Dur);
```  
  
### <a name="parameters"></a>매개 변수  
 `Dur`  
 `duration` 개체입니다.  
  
 `Mult`  
 정수 값입니다.  
  
### <a name="return-value"></a>반환 값  
 각 함수는 간격 길이가 `Mult`에 `Dur`의 길이를 곱한 값인 `duration` 개체를 반환합니다.  
  
 `is_convertible<Rep2, common_type<Rep1, Rep2>>`가 *true*가 아닌 한 첫 번째 함수는 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.  
  
 `is_convertible<Rep1, common_type<Rep1, Rep2>>`가 *true*가 아닌 한 두 번째 함수는 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.  
  
##  <a name="operator_"></a>  operator/  
 [duration](../standard-library/chrono-operators.md#operator_star) 개체에 대한 나누기 연산자입니다.  
  
```  
template <class Rep1, class Period1, class Rep2>  
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1> 
   operator/(
     const duration<Rep1, Period1>& Dur,  
     const Rep2& Div);

 
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<Rep1, Rep2>::type 
   operator/(
     const duration<Rep1, Period1>& Left,  
     const duration<Rep2, Period2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Dur`  
 `duration` 개체입니다.  
  
 `Div`  
 정수 값입니다.  
  
 `Left`  
 왼쪽 `duration` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 연산자는 길이 `Dur`을 `Div` 값으로 나눈 간격 길이를 가진 duration 개체입니다.  
  
 두 번째 연산자는 간격 길이 `Left` 및 `Right`의 비율을 반환합니다.  
  
 `is_convertible<Rep2, common_type<Rep1, Rep2>>`가 *true*이고 `Rep2`가 `duration`의 인스턴스화가 아닌 경우 외에는 첫 번째 연산자가 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.  
  
##  <a name="operator_add"></a>  operator+  
 [duration](../standard-library/duration-class.md) 및 [time_point](../standard-library/time-point-class.md) 개체를 추가합니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type 
   operator+(
      const duration<Rep1, Period1>& Left,  
      const duration<Rep2, Period2>& Right);

 
template <class Clock, class Duration1, class Rep2, class Period2>  
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,  
      const duration<Rep2, Period2>& Dur);

 
template <class Rep1, class Period1, class Clock, class Duration2>  
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,  
      const time_point<Clock, Duration2>& Time);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Time`  
 `time_point` 개체입니다.  
  
 `Dur`  
 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 함수는 `Left` 및 `Right` 간격의 합계와 동일한 시간 간격을 갖는 `duration` 개체를 반환합니다.  
  
 두 번째 및 세 번째 함수는 시점 `Time`에서 간격 `Dur`로 대체되는 시점을 나타내는 `time_point` 개체를 반환합니다.  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 작은지 여부를 확인합니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);

 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 함수는 `Left`의 간격 길이가 `Right`의 간격 길이보다 작으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  
  
 두 번째 함수는 `Left`가 `Right`보다 앞에 오면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 작거나 같은지 여부를 확인합니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 각 함수는 `!(Right < Left)`를 반환합니다.  
  
##  <a name="operator_eq_eq"></a>  operator==  
 두 `duration` 개체가 길이가 동일한 시간 간격을 나타내는지 여부 또는 두 `time_point` 개체가 동일한 시점을 나타내는지 여부를 확인합니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 함수는 `Left`와 `Right`가 길이가 같은 시간 간격을 나타내면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  
  
 두 번째 함수는 `Left`와 `Right`가 동일한 시점을 나타내면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 큰지 여부를 확인합니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 각 함수는 `Right < Left`를 반환합니다.  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 크거나 같은지 여부를 확인합니다.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `duration` 또는 `time_point` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 또는 `time_point` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 각 함수는 `!(Left < Right)`를 반환합니다.  
  
##  <a name="operator_modulo"></a>  modulo 연산자  
 [duration](../standard-library/duration-class.md) 개체에 대한 모듈로 연산용 연산자입니다.  
  
```  
template <class Rep1, class Period1, class Rep2>  
constexpr duration<Rep1, Period1, Rep2>::type 
   operator%(
      const duration<Rep1, Period1>& Dur,  
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,  
     const duration<Rep2, Period2>& Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Dur`  
 `duration` 개체입니다.  
  
 `Div`  
 정수 값입니다.  
  
 `Left`  
 왼쪽 `duration` 개체입니다.  
  
 `Right`  
 오른쪽 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 함수는 간격 길이가 `Dur` modulo `Div`인 `duration` 개체를 반환합니다.  
  
 두 번째 함수는 `Left` modulo `Right`를 나타내는 값을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<chrono>](../standard-library/chrono.md)


