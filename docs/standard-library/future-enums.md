---
title: "&lt;future&gt; 열거형 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b1f8c56de97789bea4f0923cd87e8144382e1ed0
ms.lasthandoff: 02/24/2017

---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; 열거형
||||  
|-|-|-|  
|[future_errc 열거형](#future_errc_enumeration)|[future_status 열거형](#future_status_enumeration)|[launch 열거형](#launch_enumeration)|  
  
##  <a name="a-namefutureerrcenumerationa--futureerrc-enumeration"></a><a name="future_errc_enumeration"></a>  future_errc 열거형  
 [future_error](../standard-library/future-error-class.md) 클래스에서 보고한 모든 오류에 대해 기호화된 이름을 제공합니다.  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="a-namefuturestatusenumerationa--futurestatus-enumeration"></a><a name="future_status_enumeration"></a>  future_status 열거형  
 timed wait 함수가 반환할 수 있는 이유에 대해 기호화된 이름을 제공합니다.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="a-namelaunchenumerationa--launch-enumeration"></a><a name="launch_enumeration"></a>  launch 열거형  
 템플릿 함수 [async](../standard-library/future-functions.md#async_function)에 가능한 모드를 설명하는 비트 마스크 형식을 나타냅니다.  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>참고 항목  
 [\<future>](../standard-library/future.md)




