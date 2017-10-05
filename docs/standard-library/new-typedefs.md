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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e23ea06002dc840997a0e7202f581cd81ef407c5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

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




