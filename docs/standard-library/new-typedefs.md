---
title: "&lt;new&gt; 형식 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b652d0a1eac1615d1e1b0aed1df05d6a9ee661a3
ms.lasthandoff: 02/24/2017

---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; 형식 정의
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a>  new_handler  
 이 형식은 새 처리기로 사용하기에 적합한 함수를 가리킵니다.  
  
```
typedef void (*new_handler)();
```  
  
### <a name="remarks"></a>설명  
 이 유형의 처리기 함수는 추가 저장소 요청을 충족할 수 없을 때 **operatornew** 또는 `operator new[]`에 의해 호출됩니다.  
  
### <a name="example"></a>예제  
  `new_handler`를 반환 값으로 사용하는 방법의 예제는 [set_new_handler](../standard-library/new-functions.md#set_new_handler)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [\<new>](../standard-library/new.md)




