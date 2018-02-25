---
title: "&lt;chrono&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 41ea765f98882bb0f3f1531e284ca06a6fb79067
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 함수
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>  duration_cast
 지정된 형식으로 `duration` 개체를 캐스팅합니다.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>반환 값  
 시간 간격 `Dur`을 나타내는 `To` 형식의 `duration` 개체로, 대상 형식에 맞게 조정해야 하는 경우 잘립니다.  
  
### <a name="remarks"></a>설명  
 `To`가 `duration`의 인스턴스화인 경우 이 함수는 오버로드 확인에 참여하지 않습니다.  
  
##  <a name="time_point_cast"></a>  time_point_cast
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

