---
title: "&lt;future&gt; 열거형 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 786d999dc03692c11e2c511023f1feb2c84573f8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; 열거형
||||  
|-|-|-|  
|[future_errc](#future_errc)|[future_status](#future_status)|[시작](#launch)|  
  
##  <a name="future_errc"></a>  future_errc 열거형  
 [future_error](../standard-library/future-error-class.md) 클래스에서 보고한 모든 오류에 대해 기호화된 이름을 제공합니다.  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="future_status"></a>  future_status 열거형  
 timed wait 함수가 반환할 수 있는 이유에 대해 기호화된 이름을 제공합니다.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="launch"></a>  launch 열거형  
 템플릿 함수 [async](../standard-library/future-functions.md#async)에 가능한 모드를 설명하는 비트 마스크 형식을 나타냅니다.  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>참고 항목  
 [\<future>](../standard-library/future.md)




