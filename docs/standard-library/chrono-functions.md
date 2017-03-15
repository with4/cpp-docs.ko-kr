---
title: "&lt;chrono&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9824bdc37d1ae2d1d3a8e42c727986fd2a194514
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 함수
||||  
|-|-|-|  
|[duration_cast 함수](#duration_cast_function)|[time_point_cast 함수](#time_point_cast_function)|  
  

##  <a name="a-namedurationcastfunctiona--durationcast-function"></a><a name="duration_cast_function"></a>  duration_cast 함수  
 지정된 형식으로 `duration` 개체를 캐스팅합니다.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>반환 값  
 시간 간격 `Dur`을 나타내는 `To` 형식의 `duration` 개체로, 대상 형식에 맞게 조정해야 하는 경우 잘립니다.  
  
### <a name="remarks"></a>설명  
 `To`가 `duration`의 인스턴스화인 경우 이 함수는 오버로드 확인에 참여하지 않습니다.  
  
##  <a name="a-nametimepointcastfunctiona--timepointcast-function"></a><a name="time_point_cast_function"></a>  time_point_cast 함수  
 지정된 형식으로 [time_point](../standard-library/time-point-class.md) 개체를 캐스팅합니다.  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>반환 값  
 `To` 형식의 기간이 있는 `time_point` 개체입니다.  
  
### <a name="remarks"></a>설명  
 `To`가 [duration](../standard-library/duration-class.md)의 인스턴스화가 아닌 한 이 함수는 오버로드 확인에 참여하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<chrono>](../standard-library/chrono.md)


